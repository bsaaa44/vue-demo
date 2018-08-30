<template>
    <div>
        <p>vuex test</p>
        <p>Now count is {{count}}</p>
        <p>{{getCountText}}</p>
        <button @click='test'>点我</button>
        <button @click='show = !show'>点我显示隐藏</button>
        <transition name='fade'>
          <p v-if='show'>transition test</p>
        </transition>
        <p>主分支添加了一行代码</p>
        <p>主分支又添加了一行代码</p>
        <p>ssh添加测试</p>
        <p>把仓库url换成ssh</p>
        <p>在分支添加了一行代码</p>
        <span>贮藏测试</span>
    </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  data() {
    return {
      show: false
    }
  },
  computed: {
    // count() {
    //   return this.$store.state.count
    // }

    getCountText() {
      return this.$store.getters.getCountText
    },
    ...mapState(['count'])
  },
  methods: {
    test() {
      this.$store.commit('increment')
    }
  }
}
</script>
<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active 在低于版本 2.1.8 中 */ {
  opacity: 0;
}
</style>
