<template>
  <div class="selectbox-size">
    <br>

    <!-- Default size-->
    <div>
      <span style="font-size: 14px; font-weight: bold;">1. Default size</span><br><br>
    </div>
    <div style="display: inline-flex; height: 170px;">
      <!-- size small -->
      <div :style="{ display: 'inline-block', flex: 1, maxWidth: '30%' }">
        <span style="font-size: 14px;">size: small</span><br><br>
        <ev-selectbox
          v-model="vModel0"
          :name="'box_0'"
          :size="'small'"
          :multiple="true"
          :items="items0"
        />
        <br><br>
        <span style="font-size: 12px;">value: </span>
        <span style="font-weight: bold; color: blue;">{{ vModel0 }}</span>
      </div>

      <!-- size medium -->
      <div :style="{ display: 'inline-block', flex: 1, maxWidth: '30%', marginLeft: '50px' }">
        <span style="font-size: 14px;">size: medium</span><br><br>
        <ev-selectbox
          v-model="vModel1"
          :name="'box_1'"
          :size="'medium'"
          :multiple="true"
          :items="items1"
        />
        <br><br>
        <span style="font-size: 12px;">value: </span>
        <span style="font-weight: bold; color: blue;">{{ vModel1 }}</span>
      </div>

      <!-- size large -->
      <div :style="{ display: 'inline-block', flex: 1, maxWidth: '30%', marginLeft: '50px' }">
        <span style="font-size: 14px;">size: large</span><br><br>
        <ev-selectbox
          v-model="vModel2"
          :name="'box_2'"
          :size="'large'"
          :multiple="true"
          :items="items2"
        />
        <br><br>
        <span style="font-size: 12px;">value: </span>
        <span style="font-weight: bold; color: blue;">{{ vModel2 }}</span>
      </div>
    </div>

    <!-- Custom size -->
    <div>
      <span style="font-size: 14px; font-weight: bold;">2. Custom size</span><br><br>
    </div>
    <div style="display: inline-flex; height: 180px;">
      <!-- custom size 1 -->
      <div :style="{ display: 'inline-block', flex: 1, maxWidth: '30%' }">
        <span style="font-size: 14px;">
          size: width: {{ customStyle1.width }} / height: {{ customStyle1.height }}
        </span><br><br>
        <ev-selectbox
          v-model="vModel3"
          :style="customStyle1"
          :name="'box_3'"
          :size="'small'"
          :multiple="true"
          :items="items3"
        />
        <br><br>
        <span style="font-size: 12px;">value: </span>
        <span style="font-weight: bold; color: blue;">{{ vModel3 }}</span>
      </div>

      <!-- custom size 2 -->
      <div :style="{ display: 'inline-block', flex: 1, maxWidth: '30%', marginLeft: '50px' }">
        <span style="font-size: 14px;">
          size: width: {{ customStyle2.width }} / height: {{ customStyle2.height }}
        </span><br><br>
        <ev-selectbox
          v-model="vModel4"
          :style="customStyle2"
          :name="'box_4'"
          :multiple="true"
          :items="items4"
        />
        <br><br>
        <span style="font-size: 12px;">value: </span>
        <span style="font-weight: bold; color: blue;">{{ vModel4 }}</span>
      </div>

      <!-- custom size 3 -->
      <div :style="{ display: 'inline-block', flex: 1, maxWidth: '30%', marginLeft: '50px' }">
        <span style="font-size: 14px;">
          size: width: {{ customStyle3.width }} / height: {{ customStyle3.height }}
        </span><br><br>
        <ev-selectbox
          v-model="vModel5"
          :style="customStyle3"
          :name="'box_5'"
          :multiple="true"
          :items="items5"
        />
        <br><br>
        <span style="font-size: 12px;">value: </span>
        <span style="font-weight: bold; color: blue;">{{ vModel5 }}</span>
      </div>
    </div>

    <br><br><br><br><br><br><br><br><br><br><br><br>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        vModel0: ['item_0', 'item_2'],
        vModel1: ['item_1'],
        vModel2: ['item_2', 'item_3'],
        vModel3: ['item_3'],
        vModel4: ['item_1'],
        vModel5: ['item_2'],
        items0: this.getItemList(),
        items1: this.getItemList(),
        items2: this.getItemList(),
        items3: this.getItemList(),
        items4: this.getItemList(),
        items5: this.getItemList(),
        customStyle1: { width: '100px', height: '18px' },
        customStyle2: { width: '200px', height: '80px' },
        customStyle3: { width: '300px', height: '200px' },
      };
    },
    methods: {
      getItemList() {
        let value;
        const itemList = [];

        for (let ix = 0; ix < 5; ix++) {
          value = `item_${ix}`;

          itemList.push({
            name: value,
            value,
          });
        }

        return itemList;
      },
    },
  };
</script>
<style>
  .selectbox-size {
    width: 100%;
    height: 100%;
    margin-left: 5px;
    padding-top: 10px;
    font-size: 14px;
  }
</style>
