<template>
  <div>
    <div>
      <page-header-wrapper
        title="防范能力本体"
      >
        <a-button style="margin-right: 4px; " @click="showTable1()">政府应急建设</a-button>
        <a-button @click="showTable2()">政府监管责任</a-button>
        <a-button style="margin-left: 4px;" @click="showTable3()">企业主体责任</a-button>
        <a-button style="margin-left: 395px;">区域名称</a-button>
      </page-header-wrapper>
    </div>
    <div id="table1" class="table" v-if="visible1" style="margin-top: 10px; ">
      <a-table :columns="columns1" :data-source="data1">
        <a slot="name" slot-scope="text">{{ text }}</a>
      </a-table>
    </div>
    <div id="table2" class="table" v-if="visible2" style="margin-top: 10px; ">
      <a-table :columns="columns2" :data-source="data2">
        <a slot="name" slot-scope="text">{{ text }}</a>
      </a-table>
    </div>
    <div id="table3" class="table" v-if="visible3" style="margin-top: 10px; ">
      <a-table :columns="columns2" :data-source="data3">
        <a slot="name" slot-scope="text">{{ text }}</a>
      </a-table>
    </div>
    <div style="margin-top: 10px; ">
      <a-list :grid="{ gutter: 16, xs: 1, sm: 2, md: 4, lg: 4, xl: 6, xxl: 3 }" :data-source="ldata">
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
const columns1 = [
  {
    title: '序列号',
    dataIndex: 'number1',
    key: 'number1',
    scopedSlots: { customRender: 'number1' }
  },
  {
    title: '应急建设类别',
    dataIndex: 'class1',
    key: 'class1',
    ellipsis: true
  },
  {
    title: '属性开关',
    dataIndex: 'open1',
    key: 'open1',
    ellipsis: true
  },
  {
    title: '完成情况',
    dataIndex: 'ifFinished1',
    key: 'ifFinished1',
    ellipsis: true
  },
  {
    title: '得分',
    dataIndex: 'score1',
    key: 'score1',
    ellipsis: true,
    sorter: {
      compare: (a, b) => a.score1 - b.score1,
      multiple: 2
    }
  },
  {
    title: '权重',
    dataIndex: 'weight1',
    key: 'weight1',
    ellipsis: true,
    sorter: {
      compare: (a, b) => a.weight1 - b.weight1,
      multiple: 1
    }
  },
  {
    title: '总分',
    dataIndex: 'total1',
    key: 'total1',
    ellipsis: true
  },
  {
    title: '详细内容',
    dataIndex: 'details1',
    key: 'details1',
    ellipsis: true
  },
  {
    title: '相关附件',
    dataIndex: 'appendix1',
    key: 'appendix1',
    ellipsis: true
  }
]
const columns2 = [
  {
    title: '序号',
    dataIndex: 'number2',
    key: 'number2',
    scopedSlots: { customRender: 'number2' }
  },
  {
    title: '行政属性',
    dataIndex: 'attribute2',
    key: 'attribute2',
    ellipsis: true
  },
  {
    title: '具体内容',
    dataIndex: 'details2',
    key: 'details2',
    ellipsis: true
  },
  {
    title: '完成情况',
    dataIndex: 'ifFinished2',
    key: 'ifFinished2',
    ellipsis: true
  },
  {
    title: '相关文件',
    dataIndex: 'file2',
    key: 'file2',
    ellipsis: true
  }
]

const data1 = [
  {
    number1: '',
    class1: '',
    open1: '',
    ifFinished1: '',
    score1: '90',
    weight1: '0.2',
    total1: '',
    details1: '',
    appendix1: '',
    tags: ['nice', 'developer']
  },
  {
    number1: '',
    class1: '',
    open1: '',
    ifFinished1: '',
    score1: '94',
    weight1: '0.9',
    total1: '',
    details1: '',
    appendix1: '',
    tags: ['nice', 'developer']
  },
  {
    number1: '',
    class1: '',
    open1: '',
    ifFinished1: '',
    score1: '91',
    weight1: '0.7',
    total1: '',
    details1: '',
    appendix1: '',
    tags: ['nice', 'developer']
  },
  {
    number1: '',
    class1: '',
    open1: '',
    ifFinished1: '',
    score1: '88',
    weight1: '0,5',
    total1: '',
    details1: '',
    appendix1: '',
    tags: ['nice', 'developer']
  },
  {
    number1: '',
    class1: '',
    open1: '',
    ifFinished1: '',
    score1: '76',
    weight1: '0.82',
    total1: '',
    details1: '',
    appendix1: '',
    tags: ['nice', 'developer']
  },
  {
    number1: '…',
    class1: '…',
    open1: '…',
    ifFinished1: '…',
    score1: '…',
    weight1: '…',
    total1: '…',
    details1: '…',
    tags: ['nice', 'developer']
  }
]
const data2 = [
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '…',
    attribute2: '…',
    details2: '…',
    ifFinished2: '…',
    file2: '…',
    tags: ['nice', 'developer']
  }
]

const data3 = [
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '',
    attribute2: '',
    details2: '',
    ifFinished2: '',
    file2: '',
    tags: ['nice', 'developer']
  },
  {
    number2: '…',
    attribute2: '…',
    details2: '…',
    ifFinished2: '…',
    file2: '…',
    tags: ['nice', 'developer']
  }
]

const ldata = [
  {
    title: 'Title 1'
  },
  {
    title: 'Title 2'
  },
  {
    title: 'Title 3'
  },
  {
    title: 'Title 4'
  },
  {
    title: 'Title 5'
  },
  {
    title: 'Title 6'
  }
]

export default {
  data () {
    // this.columns = columns2
    return {
      visible1: false,
      visible2: false,
      visible3: false,
      columns1,
      columns2,
      ldata,
      data1,
      data2,
      data3
    }
  },

  methods: {
    showTable1 () {
      this.visible1 = !this.visible1
    },
    showTable2 () {
      this.visible2 = !this.visible2
    },
    showTable3 () {
      this.visible3 = !this.visible3
    }
  }
}
</script>
