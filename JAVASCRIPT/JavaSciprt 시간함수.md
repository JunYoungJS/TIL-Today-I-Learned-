# Nomad Codeer Vanila JS 5.1 ~5.3

## SetInterval 함수

- Paremeter : function , delay(시간),[arg1, arg2,...]
- 함수를 정해진 시간에 따라 주기적으로 실행 (2초마다 실행)

## SetTimeOut 함수

- Parameter : function , delay(시간), [arg,arg2,...]
- 함수를 정해진 시간 후 한번 실행 (2초에 한번 )

## Date 객체

- 날짜의 형식과 관련해서 제공해줌
- new Date() , Date() 함수형식과 생성자 형식으로 호출 가능
- 날짜와 시간 과 관련된 메소드 제공 Mdn : (https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Date)

## padStart 함수

- Parameter : (targetLength,padString)
- 해당 문자열이 targetLength에 충족하지못하면 padString으로 앞부분을 채움
- 숫자가아닌 문자열만 됨

## padEnd 함수

- Parameter : (targetLength,padString)
- 해당 문자열이 targetLength에 충족하지못하면 padString으로 뒷 부분을 채움
- 숫자가 아닌 문자열만 됨

# 활용 예제

```

현재 시간을 실시간으로 보여줌
const clockTitle = document.querySelector(".js-clock");

const currentTime=()=>{
    const todayDate=new Date()
    const hours=String(todayDate.getHours()).padStart(2,"0")
    const minutes=String(todayDate.getMinutes()).padStart(2,"0")
    const seconds=String(todayDate.getSeconds()).padStart(2,"0")

    clockTitle.innerHTML=`${hours}h ${minutes}m ${seconds}s`
}

1초마다 실행 해당함수를 실행
setInterval(currentTime,1000)
```
