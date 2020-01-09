<template>
  <MyChild />
</template>

<script>

import MyChild from './child'

export default {
  name: 'ElForm',
  componentName: 'ElForm',

  components: {
    MyChild
  },

  data() {
    return {
      parentText: 'parentText'
    }
  },

  created() {
    this.$on('addField', (field) => {
      console.log(22222)
      console.log(field)
    })
  },
}

</script>
