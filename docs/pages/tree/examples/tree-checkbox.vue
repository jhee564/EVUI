<template>
  <div style="width:100%">
    <ev-tree
      :use-checkbox="true"
      :data="data"
      @on-check-change="onCheckChange"
    />
  </div>
</template>

<script>
  export default {
    data() {
      return {
        data: [
          {
            title: '@parent 1',
            expand: true,
            selected: true,
            children: [
              {
                title: 'parent 1-1',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-1-1',
                    disabled: true,
                  },
                  {
                    title: 'leaf 1-1-2',
                  },
                ],
              },
              {
                title: 'parent 1-2',
                expand: true,
                children: [
                  {
                    title: 'leaf 1-2-1',
                    checked: true,
                  },
                  {
                    title: 'leaf 1-2-1',
                  },
                ],
              },
            ],
          },
        ],
      };
    },
    methods: {
      onCheckChange(val) {
        console.log(val);
      },
    },
  };
</script>
