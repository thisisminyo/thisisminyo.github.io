---
layout: post
title: "[React] React study 02"
categories: jekyll
---

_이 포스트의 내용은 [Udemy 강좌 모던 리액트와 리덕스](www.udemy.com/course/react-redux-korean/)의 내용을 공부하며 정리한 것 입니다_


## Section 2

### 하향 데이터 플로우

- 정보와 연관되어 있는 부모 컴포넌트가 이를 가져올 권리를 가짐 (추후 추가 설명)

### class component

- state를 사용하기 시작할 때마다 클래스 기반 컴포넌트가 필요

### es6 syntax

```jsx
this.setState({ videos : videos });

// es6
this.setState({ videos });
```

### Pass data from parent to child

```jsx
<VideoList videos={this.state.videos} />

const VideoList = (props) => {
	...
}
```

### Props in components

```jsx
// functional components
{props.videos.length}

// class components
{this.props.videos.length}
```

### Looping in React

- 반복 리스트를 만들때 map을 사용하는 것을 권장
- 리액트는 배열 요소 렌더링에 유능함
- 배열 형태로 제공된 컴포넌트 내부의 태그를 렌더링 시도함
- 리액트는 배열 아이템을 렌더링 할때마다 리스트를 만드는 것으로 가정함
- 각 리스트 요소마다 키 값이 필요함

```jsx
const videoItems = props.videos.map(video => {
     return <VideoListItem key={videos.etag} video={video} />;
});

return <ul>{videoItems}</ul>;
```

### Props in child component

```jsx
const VideoItemList = (props) => {
	const video = props.video;
	...
}

//es6
const VideoItemList = ({video}) => {
	...
}
```

### String interpolation

```jsx
const url = "https://www.youtube.com/embed/" + videoId

// es6
const url = `https://www.youtube.com/embed/${videoId}`;
```

### Arrow function in the component

```jsx
<CompName propName={para => this.setState({para})} />
```

- render 메소드 안에서 화살표 함수를 사용하면 컴포넌트가 렌더링할 때마다 새로운 함수를 만들기 때문에 엄격한 비교에 의해 최적화가 깨질 수 있다.
- render 메소드 안에서 화살표 함수를 사용해도 괜찮을까요?

    이 방법은 대체로 사용해도 괜찮고, 콜백 함수로 매개변수를 전달해 주는 가장 쉬운 방법입니다. 성능 문제가 있다면 반드시 최적화를 해야 합니다.

### Loadash debounce

```jsx
import _ from "lodash";

//in render(){}
const videoSearch = _.debounce(term => {this.videoSearch(term)}, 500);

//in return()
<SearchBar onSearchTermChange={videoSearch} />
```

