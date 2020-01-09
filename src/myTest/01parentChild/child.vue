<template>
  <div>
    <span>{{ text }}</span>
  </div>
</template>

<script>
export default {
  name: 'ElFormItem',
  componentName: 'ElFormItem',
  customOption: 'foo',
  components: {
  },
  data() {
    return {
      text: '123'
    }
  },
  created() {
    console.log(this.$options)
  },
  mounted() {
    setTimeout(() => {
      // this.dispatch('ElForm', 'addField', [this])
    }, 2000)
  },
  methods: {
    dispatch(componentName, eventName, params) {
      var parent = this.$parent || this.$root
      var name = parent.$options.componentName

      while (parent && (!name || name !== componentName)) {
        parent = parent.$parent

        if (parent) {
          name = parent.$options.componentName
        }
      }
      if (parent) {
        parent.$emit.apply(parent, [eventName].concat(params))
      }
    },
  }
}

</script>
