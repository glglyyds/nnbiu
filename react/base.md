**React Router 获取路由地址，参数**
```js
import React from 'react';
import { useLocation } from 'react-router-dom';
const App = () => {
  const location = useLocation();
  return (
    <div>
      <p>当前路径：{location.pathname}</p>
      <p>查询参数：{location.search}</p>
      <p>哈希值：{location.hash}</p>
    </div>
  );
};
export default App;
```