<template>
  <div>
    <h2>{{msg}}</h2>
    <hr />
    <h3>{{$store.state.count}} -- {{count}}</h3>
    <p>
      <!-- <button @click="$store.commit('add',10)">add</button>
      <button @click="reduce">reduce</button>-->
    </p>
    <p>
      <button @click="addAction">+</button>
      <button @click="reduceAction">-</button>
    </p>
  </div>
</template>
<script >
import store from "@/vuex/store";
import { mapState, mapMutations, mapGetters, mapActions } from "vuex";
export default {
  data() {
    return {
      msg: "Hello World"
    };
  },
  computed: {
    count() {
      return this.$store.state.count;
    }
  },
  store,
  // computed: mapState({
  //   count: state => state.count
  // }),
  // computed: {
  //   ...mapState(["count"]), //扩展
  //   // count() {
  //   //   this.$store.getters.count;
  //   // }

  //   ...mapGetters(["count"])
  // },
  methods: {
    ...mapMutations(["add", "reduce"]),

    ...mapActions(["addAction", "reduceAction"])
  }
};
</script>

<style scoped>
</style>