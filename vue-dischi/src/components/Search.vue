<template>
  <div class="row justify-content-center pt-3">
      <span class="text-white text-center">With component</span>
      <select class="w-25"  @change="$emit('doSearch', inputSelect)"  v-model="inputSelect">
          <option value ="Tutti"> Tutti</option>
          <option value ="Rock"> Rock</option>
          <option value ="Pop"> Pop</option>
          <option value ="Metal"> Metal</option>
          <option value ="Jazz"> Jazz</option>
        </select>
  </div>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      inputSelect : '',
    }
  }
}
</script>

<style>

</style>