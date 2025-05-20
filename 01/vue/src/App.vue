<script>
// Options API(2.x)
// 클래스 컴포넌트
// 약속된 객체의 속성
// -- data: 뷰에서 사용할 데이터(상태)를 정의할 때 사용하는 속성
// 디렉티브
// - v-html: 데이터에 HTML태그를 넣으면 적용됨, 태그가 통째로 변경이 된다
// - v-text
// - v-pre : 컴파일의 대상으로 삼지 않게 함 -> 정적인 텍스트만 있는 페이지에 사용하는 것이 좋다.
// - v-bind: 데이터 바인딩
// - v-if: if문과 같은 역할. 조건이 맞지 않으면 렌더링도 되어있지 않다. 관련되어있는 것 중 일치하는것이 하나도 없으면 주석으로 존재의 흔적은 남는다.
// - v-show: display속성. 안보이더라도 렌더링은 되어있다.노출 상태가 자주 변경되는 요소는 -v-show가 성능적으로 더 좋다.
// - v-for: 최대 2중첩까지 사용 가능
// 축약형(기존 디렉티브를 줄여서 쓸 수 있는 문법 -> :): 일관되게 사용해야 한다.
// 3.4버전부터는 데이터와 v-bind의 속성명이 같으면 데이터 이름도 축약해서 사용이 가능하다
// Composition API(3.x)

export default {
  data() {
    return {
      condition: "F",
      fruits: ["apple", "banana", "orange"],
      userObj: {
        name: "철수",
        age: 20,
      },
    };
  },
};
</script>
<template>
  <h1 v-if="condition === 'A'">A입니다</h1>
  <h1 v-else-if="condition === 'B'">B입니다</h1>
  <h1 v-else-if="condition === 'C'">C입니다</h1>
  <h1 v-else>A ~ C가 아닙니다.</h1>
  <h1 v-show="condition === 'F'">F입니다</h1>
  <ul>
    <li v-for="(value, index) in fruits" :key="'index'">
      [{{ index }}] - {{ value }}
      <ul>
        <li v-for="(value, key) in userObj" :key>
          key: {{ key }} - value: {{ value }}
        </li>
      </ul>
    </li>
  </ul>
</template>
