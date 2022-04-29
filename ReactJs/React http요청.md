# React 에서 https 요청하는 방법

- Client에서는 백앤드 api를 통해 데이터를 가져옴
  - axios 서드파티 라이브러리를 사용
  - async await 을 사용 ,fetch,promise
- useEffect 훅을 사용하여 웹페이지 초기에 api데이터를 가져와서 렌더링시킴

- Get 요청

  - db에 저장된 데이터를 가져옴

- Post 요청
  - db에 사용자의 정보를 저장함

## fetch를 사용하여 api 데이터 가져오기 (Get 요청)

```jsx
function fetchMoviesHandler() {
  fetch("https://swapi.dev/api/films/") // 리턴값으로 promise 반환
    .then((response) => {
      return response.json();
      // 1. response를 json으로 변환
    })
    .then((data) => {
      // 2. json인 data를 가지고 api 데이터 내용 추출
      const transformedMovies = data.results.map((movieData) => {
        return {
          id: movieData.episode_id,
          title: movieData.title,
          openingText: movieData.opening_crawl,
          releaseDate: movieData.release_date,
        };
      });
    });
}
```

## async 를 사용하여 api 데이터 가져오기 (Get 요청)

```jsx
async function fetchMoviesHandler() {
  const response = await fetch("https://swapi.dev/api/films/");
  const data = await response.json();
  const transformedMovies = data.results.map((movieData) => {
    return {
      id: movieData.episode_id,
      title: movieData.title,
      openingText: movieData.opening_crawl,
      releaseDate: movieData.release_date,
    };
  });
}
```

## api 데이터 가져올때 에러처리 예시 코드

```jsx
function App() {
  const [movies, setMovies] = useState([]);
  const [isLoading, setIsLoading] = useState(false);
  const [error, setError] = useState(null);

  async function fetchMoviesHandler() {
    setIsLoading(true);
    setError(null);
    try {
      const response = await fetch("https://swapi.dev/api/film/");
      if (!response.ok) {
        throw new Error("Something went wrong");
      }

      const data = await response.json();

      const transformedMovies = data.results.map((movieData) => {
        return {
          id: movieData.episode_id,
          title: movieData.title,
          openingText: movieData.opening_crawl,
          releaseDate: movieData.release_date,
        };
      });
      setMovies(transformedMovies);
    } catch (error) {
      setError(error.message);
    }
    setIsLoading(false);
  }

  let content = <p>Found no moives</p>;
  if (movies.length > 0) {
    content = <MoviesList movies={movies} />;
  }
  if (error) {
    content = <p>{error}</p>;
  }

  if (isLoading) {
    content = <p>Loading...</p>;
  }

  return (
    <React.Fragment>
      <section>
        <button onClick={fetchMoviesHandler}>Fetch Movies</button>
      </section>
      <section>{content}</section>
    </React.Fragment>
  );
}

export default App;
```

## POST 요청 코드

```jsx
async function addMovieHandler(movie) {
  const response = await fetch(
    "https://react-http-1ca71-default-rtdb.firebaseio.com/movies.json",
    {
      method: "POST",
      body: JSON.stringify(movie),
      headers: {
        "Content-Type": "application/json",
      },
    }
  );
  const data = await response.json();
  console.log(data);
}
```
