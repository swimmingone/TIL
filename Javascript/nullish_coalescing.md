# [Javascript] Nullish coalescing operator '??'

자바스크립트의 신규 문법인 nullish 병합연산자 '??'를 사용하면
짧은 문법으로 여러 피연산자 중 값이 '확정되어있는' 변수를 찾을 수 있다.

개발을 하다보면 값이 확정되지 않아서 (예를 들어, api 요청으로 받아온 값을 변수에 할당해줘야 하는 경우) 변수에 기본값을 할당하고 싶을 때가 많은데, 이런 경우 ?? 연산자가 매우 유용하다.

전에는 비슷한 용도로 logical OR operator 인 '||' 를 사용했었는데, 어떤 차이가 있는지도 함께 정리해보겠다.

---

## '??' 사용 예시


```js
// Bad code
function printMessage(text) {
  let message = text;
  if (text == null || text == undefined) {
    message = 'Nothing to display';
  }
  console.log(message);
}
```

'??' 연산자를 사용하여 위 코드를 개선해보면 다음과 같다.

```js
// Good code
function printMessage(text) {
 const message = text ?? 'Nothing to display';
 console.log(message);
}
```


---
## '??' vs '||'

**??는 첫 번째 정의된(defined) 값을 반환한다.**

![](https://velog.velcdn.com/images/swimmingone/post/0268e9bf-1b4a-489a-812a-9c0876c35a67/image.png)

**||는 첫 번째 truthy 값을 반환한다.**

![](https://velog.velcdn.com/images/swimmingone/post/c8d43fed-ab32-4128-b907-cadb4e716a94/image.png)

---
## 참고 자료

https://www.youtube.com/watch?v=BUAhpB3FmS4&list=PLv2d7VI9OotTVOL4QmPfvJWPJvkmv6h-2&index=25


https://ko.javascript.info/nullish-coalescing-operator

