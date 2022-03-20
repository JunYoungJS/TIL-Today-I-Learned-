# BFS 알고리즘 : [참고링크](https://blog.encrypted.gg/941?category=773649#recentEntries)

## BFS 알고리즘이란 ?

- 다 차원 배열에서 각 칸을 방문할때 너비를 우선으로 방문하는 알고리즘
  - 현재 위치에서 인접한 노드들이 여러개가 있으면 해당 노드들을 전부다 방문
- 모든 노드들을 방문할떄까지 탐색한다 (완전탐색)
- 거리(cost)는 1이며 거리(cost)가 1일경우 최단경로를 구할떄도 사용할수있다. (다익스트라는 1보다큼)
- 시간복잡도는 O(N)이다

## BFS 알고리즘 동작순서

- 현재위치에서 방문할수있는 인접한 노드들을 큐에 전부다 집어넣는다
- 큐에서 꺼내 첫번쨰 과정을 반복한다
- 모든 노드들을 전부다 방문할떄까지 1,2과정 반복

## BFS와 DFS 차이점

- BFS는 현재위치에서 인접한 노드들을 전부다 우선적으로 방문하지만 DFS는 인접한노드들중 하나만 골라 우선적으로 방문하는식

## BFS 소스코드 예시 (visited와 queue를 사용 )

```c++
    while(!Q.empty()){
        pair<int,int> cur = Q.front(); Q.pop(); // 1. 큐에서 현재 위치의 좌표를 뺸다
        for(int dir = 0; dir < 4; dir++){ // 2. 현재위치의 좌표에서 인접한 상하좌우 칸을 살펴볼 것이다.
          int nx = cur.X + dx[dir]; // 2번
          int ny = cur.Y + dy[dir]; //  2번
          if(nx < 0 || nx >= n || ny < 0 || ny >= m) continue; // 3. 인접한 좌표가 범위 밖일 경우 넘어감
          if(vis[nx][ny] || board[nx][ny] != 1) continue; // 3. 이미 방문한 칸은 재 방문 x
          vis[nx][ny] = 1; // (nx, ny)를 방문했다고 명시
          Q.push({nx,ny});
        }
      }

```
