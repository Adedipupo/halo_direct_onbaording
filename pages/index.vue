<template>
  <div>
    <h1>Hello {{name}}</h1>
    <input v-model="name" type="name"/>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      name: ""
    }
  },
}
</script>
