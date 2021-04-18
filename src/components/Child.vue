<template>
  <div class="hello">
    {{pval}}
    <button @click="addValueChild()">ADD</button>
  </div>
</template>

<script lang="ts">
// import { Options, Vue } from 'vue-class-component';

// @Options({
//   props: {
//     msg: String,
//   },
// })

// export default class HelloWorld extends Vue {
//   msg!: string
// }
export default {
  props: ['pval'],
  methods: {
    addValueChild() {
      this.$emit('add', 10);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
