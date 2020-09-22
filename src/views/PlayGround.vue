<template>
  <div class="PlayGround">
    <span>메시지: {{ msg }}</span>
    <div v-html="msg"></div>
    <div v-bind:title="title">타이틀</div>
    <div>{{title.split('').reverse().join('') }}</div>
    <div>{{reverseTitle}}</div>
    <div>{{reverse()}}</div>
    <div :class="{active: isActive}" class="text-danger"> 클래스 바인딩</div>
    <div :class="['active', 'text-danger']"> 클래스 바인딩</div>
    <div v-bind:class="{ active: !isActive }">클래스 바인딩 반전</div>
    <!-- 10,11 => 같은 결과 다른 방법, 좋고 나쁜건 없음
    10~12 => 바인딩 클래스 중복도 가능하다. -->
    <div :style="{'color' : 'blue', fontSize: size + 'px'}">인라인 스타일 바인딩</div>
    <div :style="fontStyle">인라인 스타일 바인딩</div>
    <div :style="[fontStyle]">인라인 스타일 바인딩</div>

  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "PlayGround",
  components: {},
  data() {
    return {
      msg : '<p style="color:red;">안녕하세요</p>',
      title: "안녕하세요 vue.js입니다.",
      ok: true,
      firstName: "Foo",
      lastName: "Bar",
      fullName: "Foo Bar",
      isActive : true,
      size:30,
      fontStyle:{color : "orange", fontSize: "30px"}
    };
  },
  computed:{
    reverseTitle () {
      this.title
        .split("")
        .reverse()
        .join("");
      let result = this.title + "이건 computed";
      return result;
    }
  },
  watch: {
    firstName: function (val) {
      this.fullName = val + ' ' + this.lastName
    },
    lastName: function (val) {
      this.fullname = this.firstName + ' ' + val
    }
  },
  methods: {
    reverse() {
        this.title
        .split("")
        .reverse()
        .join("");
      let result = this.title + "이건 computed";
      return result;
    }
  }
}
</script>
<style lang="scss" scoped>
//scoped가 다른 css 파일에 영향을 끼치지 않는다.
.active {
  font-size: 30px;
  color:red; 
}

.text-danger {
  border:1px solid purple;
}
</style>