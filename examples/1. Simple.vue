<template>
  <div class="DatePicker">
    <input
      class="DatePicker__input"
      type="text"
      v-model="date"
      @click="showPicker = true"
    >

    <calendar
      v-if="showPicker"
      v-outside="() => showPicker = false"
      :date="date"
      @date-handler="v => date = v"
      @apply="() => showPicker = false"
    />

  </div>
</template>

<script>
// import Calendar from '../'
import Calendar from '../src/Index.vue'

export default {
  components: { Calendar },

  data () {
    return {
      date: '',
      showPicker: false
    }
  }
}
</script>

<style src="../dist/vue-convenia-calendar.css" />
