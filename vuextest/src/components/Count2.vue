<template>
  <div>
    <h2>{{msg}}</h2>
    <hr />
    <h3>{{$store.state.a.count}} -- {{count}}</h3>
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
      return this.$store.state.a.count;
    }
  }
};
</script>

<style scoped>
</style>