<template>
  <div class="view-cart">
    Cart
      <filter :callback="handleFilter" :filter-key="filterKey"></filter>
  </div>
</template>

<script>
  import Filter from '../../commons/Filter';

  export default {
    components: {
      Filter
    },
    attached () {
      document.title = 'cart';
    },
    data () {
      return {
        topic: this.$route.name,
        filterKey: this.$route.query,
        filterDatas: [
          {
            'key': 'a',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'b',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'c',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'd',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'e',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'f',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'g',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'h',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          },
          {
            'key': 'i',
            'display': '线路类型',
            'choices': [
                {'id': 0, 'display': '不限'},
                {'id': 1, 'display': 'kayak独木舟'},
                {'id': 2, 'display': 'canoe划艇'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'},
                {'id': 3, 'display': 'sup桨板'}
            ]
          }
        ]
      };
    },

    methods: {
      handleFilter (query) {
        console.log(query);
        let filterDefalut = true;
        for (var key in query) {
          if (query.hasOwnProperty(key) && query[key] !== 0) {
            filterDefalut = false;
            break;
          };
        };
        if (filterDefalut) {
          this.$route.router.go({
            name: this.topic
          });
        } else {
          this.$route.router.go({
            name: this.topic,
            query: query
          });
        };
      }
    }
  };
</script>

<style lang="scss" scoped>
  @import "../../../assets/styles/variables.scss";

  .view-cart {
  }
</style>
