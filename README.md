# refactoring


화살표함수의 사용이유?
Es5에서의 비동기상황에서는 vm = this;를 통해서 콜백함수에 들어가도 this가 새어나가지 않도록 하는 바인딩기법을 이용하였다.
하지만 Es6에서 화살표함수가 생기면서 자체적으로 this를 매칭해주기 때문에 vm = this;와 같은 방법이 필요가 없어졌다.
