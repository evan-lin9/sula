---
title: 请求
---

## 普通请求

```jsx
import React from 'react';
import { Button } from 'antd';
import { request } from './';

export default () => {

  return <Button onClick={() => {
    request({
      url: 'https://jsonplaceholder.typicode.com/todos/1',
    }).then(data => {
      console.log('data: ', data);
    })
  }}>请求</Button>
}
```

## 钩子

```jsx
import React from 'react';
import { Button } from 'antd';
import { request } from './';

export default () => {

  return <Button onClick={() => {
    request({
      url: 'https://jsonplaceholder.typicode.com/todos/1',
      converter : ({data}) => {
        return {
          ...data,
          name: 'sula'
        };
      }
    }).then(data => {
      console.log('data: ', data);
    })
  }}>请求</Button>
}
```