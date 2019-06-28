<template>
  <div class="accordion-list">
    <h2>{{ items.title }}</h2>
    <accordion-item
      v-for="(item, index) in items.sections" 
      :key="item.title"
      :name="`accordion-item-${index}`"
      :titleSlug="item.slug"
      :title="item.title"
      :body="item.body"
      :index="index"
      :hasFocus="index === focusIndex"
      @focus-previous="onFocusPrevious"
      @focus-next="onFocusNext"
      @focus-first="onFocusFirst"
      @focus-last="onFocusLast"
      @tab-pressed="onTabKey" />
  </div>
</template>

<script>
  import AccordionItem from '../accordion-item/accordion-item'

  export default {
    components: { AccordionItem },
    props: {
      items: {
        type: Object,
        required: true
      }
    },
    data() {
      return {
        focusIndex: null
      }
    },
    computed: {
      numberOfAccordionItems() {
        return this.items.sections.length - 1
      }
    },
    methods: {
      onFocusPrevious(indexAccordionItem) {
        if (indexAccordionItem !== 0) {
          this.focusIndex = indexAccordionItem - 1
          return
        }
        this.focusIndex = this.numberOfAccordionItems
      },

      onFocusNext(indexAccordionItem) {
        if (indexAccordionItem !== this.numberOfAccordionItems) {
          this.focusIndex = indexAccordionItem + 1
          return
        }
        this.focusIndex = 0
      },

      onFocusFirst() {
        this.focusIndex = 0
      },

      onFocusLast() {
        this.focusIndex = this.numberOfAccordionItems
      },

      // Reset focus state for edge case where a combination of the tab key and arrow keys don't update the focus state.
      onTabKey() {
        this.focusIndex = null
      }
    }
  }
</script>

<style>
  @import './accordion-list.css'
</style>
