<template>
  <div>
    <div style="display: inline-block">
      <page-header-wrapper
        title=" "
      >
        <div>
          <a-input-search placeholder="search something you want" enter-button @search="onSearch" />
        </div>
        <a-button-group>
          <a-button value="large" style="display: inline-block" @click="Show2()" >人为因子</a-button>
          <a-button value="large" style="display: inline-block" type="primary" @click="Show()" >自然因子</a-button>
          <a-button value="large" style="display: inline-block;margin-left: 680px;" type="primary" @click="Show3()">区域名称</a-button>
        </a-button-group>
      </page-header-wrapper>
    </div>
    <div>
      <a-table :columns="columns2" :data-source="data2" v-if="visible2">
        <a slot="name" slot-scope="text">{{ text }}</a>
      </a-table>
      <a-table :columns="columns" :data-source="data" v-if="visible">
        <a slot="name" slot-scope="text">{{ text }}</a>
      </a-table>
    </div>
    <div>
      <a-list :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }" :data-source="data3" v-if="visible3">
        <a-list-item slot="renderItem" slot-scope="item">
          <a-card :title="item.title">
            Card content
          </a-card>
        </a-list-item>
      </a-list>
    </div>
  </div>
</template>
<script>
import Bar from '@/components/Charts/TransferBar'
const columns = [
  {
    title: '属性类',
    dataIndex: 'class',
    key: 'class',
    scopedSlots: { customRender: 'class' }
  },
  {
    title: '属性名',
    dataIndex: 'name',
    key: 'name',
    ellipsis: true
  },
  {
    title: '属性开关',
    dataIndex: 'open',
    key: 'open',
    ellipsis: true
  },
  {
    title: '权重值',
    dataIndex: 'weight',
    key: 'weight',
    ellipsis: true
  },
  {
    title: '当前区域属性值',
    dataIndex: 'value',
    key: 'value',
    ellipsis: true
  },
  {
    title: '属性得分',
    dataIndex: 'score',
    key: 'score',
    ellipsis: true
  },
  {
    title: '属性总分',
    dataIndex: 'total',
    key: 'total',
    ellipsis: true
  },
  {
    title: '备注',
    dataIndex: 'other',
    key: 'other',
    ellipsis: true
  }
]
const columns2 = [
  {
    title: '属性类',
    dataIndex: 'class',
    key: 'class',
    scopedSlots: { customRender: 'class' }
  },
  {
    title: '属性名',
    dataIndex: 'name',
    key: 'name',
    ellipsis: true
  },
  {
    title: '属性开关',
    dataIndex: 'open',
    key: 'open',
    ellipsis: true
  },
  {
    title: '权重值',
    dataIndex: 'weight',
    key: 'weight',
    ellipsis: true
  },
  {
    title: '当前区域属性值',
    dataIndex: 'value',
    key: 'value',
    ellipsis: true
  },
  {
    title: '属性得分',
    dataIndex: 'score',
    key: 'score',
    ellipsis: true
  },
  {
    title: '属性总分',
    dataIndex: 'total',
    key: 'total',
    ellipsis: true
  },
  {
    title: '备注',
    dataIndex: 'other',
    key: 'other',
    ellipsis: true
  }
]

const data = [
  {
    key: '1',
    class: '风',
    name: '风速',
    open: '开',
    weight: '0.3％',
    value: '2m/s',
    score: '2',
    total: '5',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '2',
    class: '风',
    name: '风力',
    open: '开',
    weight: '2％',
    value: '三级',
    score: '3',
    total: '5',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '3',
    class: '风',
    name: '风向',
    open: '关',
    weight: '',
    value: '',
    score: '',
    total: '',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '4',
    class: '降水',
    name: '降水量',
    open: '开',
    weight: '',
    value: '',
    score: '',
    total: '',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '5',
    class: '降水',
    name: '降水时间',
    open: '关',
    weight: '',
    value: '',
    score: '',
    total: '',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '6',
    class: '…',
    name: '…',
    open: '…',
    weight: '…',
    value: '…',
    score: '…',
    total: '…',
    other: '…',
    tags: ['nice', 'developer']
  }
]
const data2 = [
  {
    key: '1',
    class: '凶器',
    name: '刀',
    open: '开',
    weight: '',
    value: '',
    score: '',
    total: '',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '2',
    class: '凶器',
    name: '棍棒',
    open: '开',
    weight: '',
    value: '',
    score: '',
    total: '',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '3',
    class: '凶器',
    name: '枪支',
    open: '关',
    weight: '',
    value: '',
    score: '',
    total: '',
    other: '',
    tags: ['nice', 'developer']
  },
  {
    key: '4',
    class: '…',
    name: '…',
    open: '…',
    weight: '…',
    value: '…',
    score: '…',
    total: '…',
    other: '…',
    tags: ['nice', 'developer']
  }
]
const data3 = [
  {
    title: '和平区'
  },
  {
    title: '河西区'
  },
  {
    title: '河北区'
  },
  {
    title: '河东区'
  },
  {
    title: '南开区'
  },
  {
    title: '红桥区'
  },
  {
    title: '东丽区'
  },
  {
    title: '北辰区'
  },
  {
    title: '西青区'
  },
  {
    title: '津南区'
  },
  {
    title: '蓟州区'
  },
  {
    title: '宁河区'
  },
  {
    title: '武清区'
  },
  {
    title: '静海区'
  },
  {
    title: '宝坻区'
  },
  {
    title: '滨海新区'
  }
]

export default {
  components: { Bar },
  data () {
    this.columns = columns
    return {
      visible: true,
      visible2: false,
      visible3: false,
      data,
      columns,
      data2,
      columns2,
      data3
    }
  },
  methods: {
    Show () {
      this.visible = !this.visible
    },
    Show2 () {
      this.visible2 = !this.visible2
    },
    onSearch () {
      console.log()
    },
    Show3 () {
      this.visible3 = !this.visible3
    }
  }
}
</script>
