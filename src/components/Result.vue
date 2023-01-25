<template>
  <p>Result is {{ score }} ms</p>
  <div v-if="score<300">
        Fast Fast Fast!!
  </div>
  <div v-else-if="score>300 && score<600">
        Not Good But Not Bad
  </div>
  <div v-else>
       Do you even have hands?
  </div>

</template>

<script>
export default {
props:[
    'score',
]
}
</script>

<style>

</style>