<template>
  <div class="event">
    <h1>Event Page : {{pageH1}}</h1>
    <button v-on:click="counter += 1">Add 1</button>
    <!-- <button @click="counter += 1">Add 1</button> 약어  -->
    <p>위 버튼을 클릭한 횟수는 {{ counter }} 번 입니다.</p>
    <!-- `greet`는 메소드 이름으로 아래에 정의되어 있습니다 -->
    <div @click="greet">Greet</div>
    <button v-on:click="say('hi')">Say hi</button>
    <button v-on:click="say('what')">Say what</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Event",
  props: ["pageH1"],
  components: {},
  data() {
    return {
      counter: 0,
      name: "Vue.js"
    };
  },
  computed: {},
  methods: {
    greet: function(event) {
      //메소드 안에서 사용하는 'this'는 vue인스턴스를 가리킵니다.
      alert("Hello🤩" + this.name + "!");
      //'event'는 네이티브 DOM 이벤트입니다.
      console.log(event);
      if (event) {
        alert(event.target.tagName);
      }
    },
    say: msg => {
      alert(msg);
      event.preventDefault(); // 새로고침 막기
      event.stopPropagation(); // 이벤트 상위 엘리먼트 전달 중지
    }
  }
};
</script>
<style lang="scss" scoped>
.event button {
  border-radius: 5px;
  padding: 10px;
  margin: 20px;
  box-shadow: 3px 4px 4px #888;
}
</style>