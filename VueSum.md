# Veu js

* method의 함수 정의와 addEventListner를 정의할 때, arrow function을 사용하지 말자.

```javascript
const app = new Vue({
    // Vue 인스턴스
    el: 'app',
    
    data: {
        자료이름(identifier): 값,
    },
    
    // Vue 인스턴스가 사용할 메소드들
    methods: {
        함수정의: {},
    },
    
    // '미리' 계산 된 값을 반환 -> 캐싱
    computed: {},
    
    //
    watch: {},
})
```



```html
<p v-for></p>

<p v-if v-else v-else-if></p>

<p v-model></p>

<p v-on:이벤트></p> <p @이벤트></p>

<p v-bind:html속성이름></p> <p :html속성이름></p>

<p v-html></p>

<p v-show></p>
```



## Props

```javascript
// 1. Array로 표현

props: ['category']

// 2. Key: Value 로 자료형(JavaScript 자료형: Number, String, Array ...) 표현
props: {
	'category': String,
}

// 3. Object로 옵션 추가
props: {
    category: {
        type: String,
        required: true,
        validator: function(value) {
            if (value.length !== 0){
                return true
            } else {
                return false
            }
        }
    }
}
```



## Vue-cli

vue cli 설치

```
npm install -g @vue/cli
```

프로젝트 실행

```
vue create [cli-name]
```

서버 돌리기

```
npm run serve
```

axios 설치

```
npm install axios
```

* env 파일에 넣기

`.env.local` 내에 숨겨놓을 내용 작성

쓰이는 곳에 `process.env.env내의변수이름`





## Youtube Search

1. onInputChange 메서드 호출
2. Youtube API 요청
3. Youtube 응답 받고
4. Youtube Response 비디오 리스트 App Component의 data로 저장
5. data가 업데이트 되면, 컴포넌트가 템플릿을 다시 렌더링함(Vue가 해줌)
6. VideoList에서 변경된 결과를 보여줌

