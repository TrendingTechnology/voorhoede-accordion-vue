<template>
  <article>
    <a :name="titleSlug"></a>
    <h3>
      <button 
        :aria-expanded="`${open}`"
        :aria-controls="titleSlug"
        :ref="`button-${titleSlug}`"
        :data-index="index"
        @click="onButtonClick">
          <slot name="accordion-item-header"></slot>
      </button>
    </h3>

    <div v-show="open" :id="titleSlug">
      <slot name="accordion-item-panel"></slot>
    </div>
  </article>
</template>

<script>
  export default {
    props: {
      titleSlug: {
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
