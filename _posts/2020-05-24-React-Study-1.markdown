---
layout: post
title: "[React] React study 01"
categories: jekyll
---

_이 포스트의 내용은 [Udemy 강좌 모던 리액트와 리덕스](www.udemy.com/course/react-redux-korean/)의 내용을 공부하며 정리한 것 입니다_

## Section 1

### component

그때그때 필요한 컴포넌트의 종류가 다르다!

- function component : state를 가질 수 없음.
- class component : 내부적인 정보를 저장하려 할때 사용, state를 가질 수 있음

- constructor
    - 모든 javascript 클래스가 가지고 있음
    - 첫번째로 실행됨
    - 클래스가 실행될때마다 자동적으로 실행됨
    - 클래스 안에서 변수나 상태값을 초기화 하는데 이용됨.
    - super : 부모 클래스 (Component) 의 메소드를 소환할 수 있음. (CS 객체지향 프로그래밍 참조)
    - constructor 함수 안에서만 this.state = 로 스테이트를 변화시킬 수 있음

    ```jsx
    class ClassName extends Component {
    	constructor(props){
    		super(props);

    		this.state = { term: '' }; // Object
    	}
    }
    ```

    - 컴포넌트 안 다른 곳에서는 this.setState를 이용해서 사용

    ```jsx
    render(
    	// this.state.term = event.target.value // NO!!!!!!!!
    	return <input Onchange={event => this.setState({ term : event.target.value })} />;
    );
    ```

### Syntactic sugar

```jsx
import React, { Component } from 'react';
//const Component = React.Component;
```

