<template>
  <div @keydown.up.down.35.36.9="onKeyDown">
    <accordion-item
      v-for="(item, index) in items.sections" 
      :key="item.title"
      :titleSlug="item.slug"
      :index="index"
      :hasFocus="index === focusIndex">
      <template v-slot:accordion-item-header>
        {{ item.title }}
      </template>

      <template v-slot:accordion-item-panel>
        <div v-html="item.body"></div>
      </template>
    </accordion-item>
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
      onKeyDown(event) {
        const key = event.which.toString()
        
        switch(key) {
          // Up key
          case '38':
            this.onFocusPrevious(event.target)
            break
          // Down key
          case '40':
            this.onFocusNext(event.target)
            break
          // Home key
          case '36':
            this.onFocusFirst(event.target)
            break
          // End key
          case '35':
            this.onFocusLast(event.target)
            break
          case '9':
            this.onTabPressed()
            break
         default:
           return false
        }
      },

      onFocusPrevious(element) {
        const indexAccordionItem = Number(element.getAttribute('data-index'))
        if (indexAccordionItem !== 0) {
          this.focusIndex = indexAccordionItem - 1
          return
        }
        this.focusIndex = this.numberOfAccordionItems
      },

      onFocusNext(element) {
        const indexAccordionItem = Number(element.getAttribute('data-index'))
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
      onTabPressed() {
        this.focusIndex = null
      }
    }
  }
</script>
