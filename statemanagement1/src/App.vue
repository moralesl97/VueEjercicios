<template>
  <div id="app">
    <AppHeader />
    <div class="flex flex-col md:flex-row">
      <AppProfileForm @submit="update($event)" />
      <AppProfileDisplay :formData="formData"/>
    </div>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppProfileForm from './components/AppProfileForm.vue'
import AppProfileDisplay from './components/AppProfileDisplay.vue'

export default {
  components: {
    AppHeader,
    AppProfileForm,
    AppProfileDisplay,
  },
  data() {
    return {
      formData: {}
    }
  },
  methods: {
    update(formData) {
      // eslint-disable-next-line no-console
      console.log(formData)
      this.formData = formData
    }
  }
}
</script>
