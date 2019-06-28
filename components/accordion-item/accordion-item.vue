<template>
  <div class="accordion-item" @keydown.up.down.35.36.9="onKeyDown">
    <a :name="titleSlug"></a>
    <h3 class="accordion-item__title">
      <button 
        type="button"
        class="accordion-item__button"
        :class="{ 'is-open': open }"
        :aria-expanded="`${open}`"
        :aria-controls="titleSlug"
        :ref="`button-${titleSlug}`"
        @click="onButtonClick">
          {{ title }}
      </button>
    </h3>
    <div 
      v-show="open"
      class="accordion-item__body"
      :class="{ 'is-open': open }"
      :id="titleSlug"
      v-html="body">  
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      titleSlug: {
        type: String,
        required: true
      },
      title: {
        type: String,
        required: true
      },
      body: {
        type: String,
        required: true
      },
      name: {
        type: String,
        required: true
      },
      hasFocus: {
        type: Boolean,
        default: false
      },
      index: {
        type: Number,
        required: true
      },
    },
    data() {
      return {
        open: false
      }
    },
    methods: {
      onButtonClick() {
        this.open = !this.open
      },
      onKeyDown() {
        const key = event.which.toString()
        
        switch(key) {
          // Up key
          case '38':
            this.$emit('focus-previous', this.index)
            break
          // Down key
          case '40':
            this.$emit('focus-next', this.index)
            break
          // Home key
          case '36':
            this.$emit('focus-first', this.index)
            break
          // End key
          case '35':
            this.$emit('focus-last', this.index)
            break
          case '9':
            this.$emit('tab-pressed')
            break
         default:
           return false
        }
      },
    },
    watch: {
      hasFocus(newValue) {
        if (newValue) {
          this.$refs[`button-${this.titleSlug}`].focus()
        }
      }
    }
  }
</script>

<style>
  @import './accordion-item.css'
</style>
