<template>
    <div class="main">
        <Info/>
        <Fields @selected='selected' :data="select"/>
        <template v-if="select.selected && select.selected != 0">
            <div class="order">
                <MyOrder :data='select' 
                         :cut='cut_wrap.cut'
                         :wrap='cut_wrap.wrap'
                         @selected='selected'
                         @cut_wrap='getCutWrap' 
                         class="myOrder" />
                <Ordering class="ordering" 
                          :prop_cut='cut_wrap.cut'
                          :prop_wrap='cut_wrap.wrap' 
                          @cut_wrap='getCutWrap'/>
            </div>
        </template>

    </div>
</template>

<script>
import Info from './Info.vue'
import Fields from './Fields.vue'
import MyOrder from './MyOrder.vue'
import Ordering from './Ordering.vue'

export default {
  name: 'Main',
  components: {
    Info,
    Fields, 
    MyOrder,
    Ordering,
  },
  data() {
      return {
        select: {},
        orderData: {},
        cut_wrap: {cut: false, wrap: false},
      }
  },
  methods: {
      selected(data) {
          this.select = data;
      },
      getCutWrap(data) {
          this.cut_wrap = data
      }
  }
}
</script>

<style scoped>
.main {
    margin: 0 auto;
    width: 65%;
}
.order {
    display: flex;
    align-items:flex-start;
}
.myOrder, .ordering {
    width: 50%;
}
.myOrder {
    margin-right: 20px;
}
.ordering{
    margin-left: 20px;
}
</style>
