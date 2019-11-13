<template>
    <Flipper 
        :flipKey="active" 
        spring="gentle"
        :staggerConfig="staggerConfig"
        :decisionData="active"
    >
        <ul class="list">
            <li v-for="item in items" :key="item" @click="onClick(item)">
                <ListItem :item="item" 
                    :expanded="active === item"
                />
            </li>
        </ul>
    </Flipper>
</template>

<script>
import ListItem from './ListItem'
import { Flipper } from "vue-flip-toolkit"

export default {
  components: {ListItem, Flipper},
  data () {
    return {
      items: [1, 2, 3, 4, 5],
      active: 0,
      staggerConfig: {
        listItem: {
            reverse: true,
            speed: 5
        }
      }
    }
  },
  computed: {
      spring() {
          return {
            stiffness: 30,
            damping: 20
        }
      }
  },
  methods: {
    onClick (item) {
      this.active = this.active === item ? 0 : item;
      this.staggerConfig.listItem.reverse = this.active !== 0;
    }
  }
}
</script>
