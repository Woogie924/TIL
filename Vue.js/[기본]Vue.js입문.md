## 👌 Vue.js란 무엇인가?
MVVM 패턴의 ViewModel 레이어에 해당하는 화면단 라이브러리
![](https://joshua1988.github.io/images/posts/web/vuejs/view-model.png)

- **데이터 바인딩**과 **화면 단위를 컴포넌트 형태로 제공하며, 관련 API를 지원**하는데에 궁극적인 목적이 있음
- Angular에서 지원하는 **양방향 데이터 바인딩** 을 동일하게 제공
- 하지만 **컴포넌트 간 통신**의 기본 골격은 Readct의 **단방향 데이터 흐름(부모->자식)**을 사용
- 다른 FrontEnd FrameWork(Angular, React)와 비교했을 때 상대적으로 가볍고 빠름
- 문법이 단순하고 간결하여 **초기 학습 비용이 낮고 누구나 쉽게 접근 가능**

<br>

## 👌 MVVM 패턴이란?
위키에 명시된 것처럼, Backend 로직과
Client 의 마크업 & 데이터 표현단을 분리하기 위한
구조로 전통적인 MVC 패턴의 방식에서 기인하였다. 
간단하게 생각해서 화면 앞단의 회면 동작 관련 로직과 뒷단의 
DB 데이터 처리 및 서버 로직을 분리하고, 
뒷단에서 넘어온 데이터를 Model 에 담아 View 로 넘어주는 중간 지점이라고 보면 되겠다.

![](https://joshua1988.github.io/images/posts/web/vuejs/mvvm-pattern.png)

## Vue.js 시작하기
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Vue.js Sample</title>
  </head>
  <body>
    <div id="app">
      {{ message }}
    </div>

    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    <script>
      new Vue({
        el: "#app",
        data: {
          message: "Hello Vue.js!"
        }
      });
    </script>
  </body>
</html>
```
- CND으로 코드 땡겨오고, 바로 Vue 인스턴스 생성

## Vue Instance
### Vue Instance 생성자
- Vue 생성자 함수를 이용하여 인스턴스를 생성하는 방법을 아래와 같다.
```JavaScript
new Vue({
  // instance option properties
});
```
- data, template, el, methods, life cycle, hook 등의 **인스턴스 옵션 속성** 포함할 수 있다.
```JavaScript
new Vue({
  // instance option properties
  template: "",
  el: "",
  methods: {}
  // ...
});
```

### Vue Instance 초기화 Life cycle
- 데이터 관찰
- 템플릿 컴파일
- DOM 에 객체 연결
- 데이터 변경시 DOM 업데이트
아래는 커스텀 로직입니다.
```JavaScript
new Vue({
  data: {
    a: 1
  },
  created: function() {
    // this 는 vm 을 가리킴
    console.log("a is: " + this.a);
  }
});
```
- LifeCycle 단계에 따라 `created`, `mounted`, `updated`, `destroyed` 등 사용할 수 있다.
- 뷰에서는 따로 Controller를 갖고 있지 않다.


## ❤참고
- [joshua1988](https://joshua1988.github.io/)
- [시작하기 -- Vue.js](https://kr.vuejs.org/v2/guide/index.html)
