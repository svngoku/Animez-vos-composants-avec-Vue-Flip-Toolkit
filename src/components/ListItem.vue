<template>
  <Flipped 
    :flipId="flipId" :shouldInvert="shouldFlip"
    @on-start="onStart"
    stagger="listItem">
    <Flipped :inverseFlipId="flipId">
        <div class="listItem" :class="{isExpanded: expanded}">
        <div class="listItemContent">
          <Flipped :flipId="flipIdAvatar" :shouldFlip="shouldFlip">
            <div class="avatar"></div>
          </Flipped>
          <div class="description">
            <Flipped 
              :shouldFlip="shouldFlip" 
              v-for="p in paragraphs"
              stagger="listItemContent"
              :key="p"  :flipId="`listItem-${item}-${p}`">
              <div></div>
            </Flipped>
          </div>
          <div class="additional-content" v-if="expanded">
            <div></div>
            <div></div>
            <div></div>
          </div>
        </div>
      </div>
    </Flipped>
  </Flipped>
</template>

<script>
  import { Flipped } from 'vue-flip-toolkit';
  export default {
    data() {
      return {
        paragraphs: [1,2,3,4],
        Flip: true
      }
    },
    components:{Flipped},
    methods: {
      shouldFlip(prev, current) {
        // global.console.log(prev, current)
        // soit l'element quoi souhaite afficher et l'element actuel 
        //  ou celui que l'on veut cacher est l'element actuel
        return prev === this.item || current === this.item;
      },
      onStart({el}) {
        // ajouter la transition du css --> l'element
        el.classList.add('animated-in');
      }
    },
    computed: {
      flipId() {
        return `listItem-${this.item}`
      },
      flipIdAvatar() {
        return `listItem-avatar-${this.item}`
      }
    },
    props: {
      item: Number,
      expanded: Boolean
    }
  }
</script>
