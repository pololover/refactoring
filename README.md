# refactoring


화살표함수의 사용이유?
Es5에서의 비동기상황에서는 vm = this;를 통해서 콜백함수에 들어가도 this가 새어나가지 않도록 하는 바인딩기법을 이용하였다.
하지만 Es6에서 화살표함수가 생기면서 자체적으로 this를 매칭해주기 때문에 vm = this;와 같은 방법이 필요가 없어졌다.


vuex : vue 상태관리패턴 라이브러리

state : 데이터 저장공간
actions : dispatch를 통해서 실행.
mutations : actions내부에서 데이터 조작을 통해서 접근가능한 부분. 

컴포넌트 설계는 중복되는 코드의 값을 줄여줄 수 있어 리팩토링에 있어 가장 우선시 되는 것이다. 
이를 대비해 공통컴포넌트를 설계한 뒤 라우터의 name 또는 query를 통해서 분기별 처리를 할 수 있다.

컴포넌트를 분리할 때 computed를 통해서 공통컴포넌트 변수를 다룰 수 있다. 
또 이는 template v-if를 통해서 분기별처리를 할 수 있다. 재사용성이 증가되기에 적극적으로 이 방법을 토대로 리팩토링 하는게 좋은 것처럼 보인다.

vue의 slot을 통해서 한껏 코드를 유연하게 짤 수 있다. 
slot은 상위에서 데이터를 주고 하위에서는 받는 것인데 이 과정을 하위컴포넌트에서 빈칸으로 뚫어놓음으로써 상위 컴포넌트가 무엇이든간에 slot name만 참조가 된다면 원하는 데이터를 삽입할 수 있다. 

props와 emit을 이용해서 이벤트를 작동시킬 수 있지만 컴포넌트간의 관계가 멀리 떨어져있는 경우라면 eventBus를 이용하는 것이 좋다. 이는 bus라는 객체에 이벤트들을 담거나 제거시킴으로써 거리가 먼 컴포넌트 사이에서 이벤트를 적용할 때 효율적이다.

하이오더 컴포넌트 : 컴포넌트에서 반복되는 코드들을 공통으로 다루기 위해서 사용하는 것이다. 상위 컴포넌트에서 created나 render, name등과 같은 많은 부분을 재사용할 수 있기에 이를 이용하는 것이 가시성 및 접근성에 효과적이라고 볼 수 있다. 
