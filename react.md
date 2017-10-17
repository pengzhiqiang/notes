## redux 
- store：状态容器

```
import {createStore} from 'redux'
const store = createStore(fn)
```

- state：数据状态，应该和view一一对应
```
const state = store.getState()
```

- action：动作（用户和view产生的交互打包成一个对象发送个store，使数据状态发生改变）
```
const action = {
    type:"ACTION_NAME",  //动作的名称
    data:"PRELOAD_DATA"  //携带的数据
}
```

- store.dispatch()：运输器（将动作action 运输至store）

```
store.dispatch(action)
```

- reducer： 接收器（接收运输器传递过来的action并做计算）
```
let reducer = (state, action) => {
    //接收action并触发不同的stage操作
    switch(action.type):
        case 'ACTION_NAME_1':
            return state + PRELOAD_DATA_1
        case 'ACTION_NAME_2'：
            return state + PRELOAD_DATA_2
}
```
- store.subscribe(listener)：监听器（state发生改变是触发）
```
let listener = () => {
    let newState = store.getState();
    someComponent.setState(newState);
}
```

- 完整流程
```
let store = createStore(reducer) 
store.dispatch(action)
store.subscribe(listener)
```




