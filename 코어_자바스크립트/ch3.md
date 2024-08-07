## chapter 3 this

### 상황에 따라 달라지는 this

자바스크립트에서 this 는 기본적으로 실행 컨텍스트가 생성될 때 함께 결정됩니다. 실행 컨텍스트는 함수를 호출할 때 생성되므로, 바꿔 말하면 `this 는 함수를 호출할 때 결정`된다고 할 수 있습니다.

this 에는 호출한 주체에 대한 정보가 담깁니다. 어떤 함수를 메서드로서 호출하는 경우 호출 주체는 바로 함수명(프로퍼티명) 앞의 객체입니다. 점 표기법의 경우 마지막 점 앞에 명시된 객체가 곧 this 가 되는 것입니다.

ES6 에서는 함수 내부에서 this 가 전역객체를 바라보는 문제를 보완하고자, this 를 바인딩하지 않는 화살표 함수를 새로 도입했습니다. 화살표 함수는 실행 컨텍스트를 생성할 때 this 바인딩 과정 자체가 빠지게 되어, 상위 스코프의 this를 그대로 활용할 수 있습니다.

### 명시적으로 this 를 바인딩하는 방법

bind 메서드는 ES5에서 추가된 기능으로, call 과 비슷하지만 즉시 호출하지는 않고 넘겨받은 this 및 인수들을 바탕으로 새로운 함수를 반환하기만 하는 메서드입니다.

```jsx
Function.prototype.bind(thisArg[, arg1[,...])
```

ES6 에 새롭게 도입된 화살표 함수는 실행 컨텍스트 생성 시 `this` 를 바인딩하는 과정이 제외됐습니다. 즉, 이 함수 내부에는 this 가 아예 없으며, 접근하고자 하면 스코프 체인상 가장 가까운 `this` 에 접근하게 됩니다.

```jsx
var obj = {
  outer: function() {
    console.log(this);
    var innerFunc = () => {
      console.log(this);
    };
    innerFunc();
  }
};
obj.outer();
```

이렇게 하면 별도의 변수로 this 를 우회하거나 `call / apply / bind` 를 적용할 필요가 없어 더욱 간결하고 편리합니다.
