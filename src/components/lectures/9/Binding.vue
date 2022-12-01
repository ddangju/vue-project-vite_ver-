<template>
  <div>
    <!-- v-bind는 class에 합칠 수 있다. -->
    <p v-bind:class="{ active: isActive }">내용입니다</p>
    <button v-on:click="handleClick">버튼</button>
    <!-- 주의할 점 -->
    <p v-bind:class="classObject">여기 텍스트</p>
  </div>
</template>

<script>
import { ref, reactive, computed} from "vue";

export default {
  setup() {
    const isActive = ref(true);
    const handleClick = () => {
      isActive.value = !isActive.value;
    };
    // const classObject = reactive({
    //   active: true,
    // });
    const classObject = computed(() => {
      return {
        active: true && true,
        "text-danger": true && true
      }
    })
    // 주의할 점 return은 호출이 아니라 객체로!!! 반환한다. 
    return {
      isActive,
      handleClick,
      classObject,
    };
  },
};
</script>

<style scoped>
.active {
  color: red;
}
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
