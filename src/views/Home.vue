<template>
  <div>
    <v-row>
      <v-col cols="12">
        <v-select
          :items="area0"
          item-title="val"
          item-value="idx"
          label="소속명"
          return-object
          single-line
          @update:modelValue="groupSelected"
        ></v-select>
      </v-col>
      <v-col cols="12" v-if="newArr.length > 0">
        <v-select
          :items="newArr"
          label="소속명"
          single-line
          @update:modelValue="fianlSelected"
        ></v-select>
        <!-- item-title="val"
          item-value="idx" -->
      </v-col>
    </v-row>
  </div>
</template>

<script>
import { generateCodeFrame } from "vue/compiler-sfc";

export default {
  data: () => ({
    newArr: [],
    depth1: '',
    depth2: '',

  }),

  methods: {
    groupSelected(val) {
      console.log("Val : ", val);
      this.depth1 = val.val
      this.generate(val.idx);
    },

    generate(idx) {
      console.log("Idx: ", idx);
      switch (idx) {
        case 1:
          this.newArr = this.area1;
          break;
        case 2:
          this.newArr = this.area2;
          break;
      }
      // let newArr = window[this.area`${idx}`]
      // console.log('New arr : ', newArr)
    },

    fianlSelected(val) {
      console.log("Final : ", val, " depth 1 : ", this.depth1);
    },
  },

  mounted() {
    console.log("Tihis sis...........");

    
    console.log("Test : ");
  },
};
</script>
