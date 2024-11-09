  <template>
      <Calculator />
  </template>

<script>
import Calculator from './components/Calculator/index.vue';

export default {
  name: 'App',
  components: {
    Calculator,
  }
};
</script>

<style>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app{
  display: flex;
  width: 100vw;
  height: 100vh;
}

body{
  background-color: #1f1f1f;

}
</style>