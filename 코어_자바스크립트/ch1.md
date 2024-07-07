## chapter 1. 데이터 타입

### 데이터 타입의 종류

기본형 : number, string, boolean, null, undefined 등

참조형 : object, array, Function, Date, RegExp

기본형은 할당이나 연산시 값을 담긴 주솟값을 바로 복제하는 반면, 참조형은 값이 담긴 주솟값들로 이루어진 묶음을 가리키는 주솟값을 복제한다.

### 데이터 할당

<img width="516" alt="image" src="https://github.com/hye-ung97/record-books/assets/117243197/c8041a20-fd2b-41cb-a22a-f0ceab4f1818">


### undefined 와 null

undefined 를 반환하는 경우

1. 값을 대입하지 않은 변수. 즉 데이터 영역의 메모리 주소를 지정하지 않은 식별자에 접근할 때
2. 객체 내부의 존재하지 않는 프로퍼티에 접근 하려고 할 때
3. return 문이 없거나 호출되지 않는 함수의 실행 결과

<br>

비어 있음을 명시적으로 나태내고 싶을 때는 undefined 가 아닌 `null` 을 쓰면 됩니다.

`undefined` 는 오직 값을 대입하지 않은 변수에 접근하고자 할 때 자바스크립트 엔진이 반환해주는 값.
