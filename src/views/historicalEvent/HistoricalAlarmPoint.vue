<template>
  <page-header-wrapper>
    <a-card :bordered="false">
      <div class="table-page-search-wrapper">
        <a-form layout="inline">
          <a-row :span="50">
            <a-col :span="6">
              <a-form-item label="区域名称">
                <a-input autosize="true" placeholder="请输入区域名称"></a-input>
              </a-form-item>
            </a-col>
            <a-col :span="2">
              <a-button type="primary">查询</a-button>
            </a-col>
            <a-col :span="2" :offset="13">
              <a-button type="primary" @click="showTable()">显示/隐藏区域名称</a-button>
            </a-col>
          </a-row>
          <a-list item-layout="horizontal" :data-source="dataSource" v-if="visible">
            <a-list-item slot="renderItem" slot-scope= "item">
              <a-list-item-meta
                description="点击查看历史报警点">
              <a slot="title" @click="jumpToTable()">{{item.title}}</a>
              </a-list-item-meta>
            </a-list-item>
          </a-list>
          <a-table :columns="columns" :data-source="alarmPoint" v-if="viewable" @change="onChange"></a-table>
        </a-form>
      </div>
    </a-card>
  </page-header-wrapper>
</template>

<script>
import UserLayout from '@/layouts/UserLayout'
const dataSource = [
  {
    title: '和平区'
  },
  {
    title: '河东区'
  },
  {
    title: '河西区'
  },
  {
    title: '南开区'
  },
  {
    title: '河北区'
  },
  {
    title: '红桥区'
  },
  {
    title: '东丽区'
  },
  {
    title: '西青区'
  },
  {
    title: '津南区'
  },
  {
    title: '北辰区'
  },
  {
    title: '武清区'
  },
  {
    title: '宝坻区'
  },
  {
    title: '滨海新区'
  },
  {
    title: '宁河区'
  },
  {
    title: '静海区'
  },
  {
    title: '蓟州区'
  }
]
const alarmPoint = [
  {
    key: '1',
    coords: '(111,111)',
    time: '2020-10-10-21:48',
    index: '80',
    condition: '已处理',
    detail: ' ',
    comment: ' '
  },
  {
    key: '2',
    coords: '(222,222)',
    time: '2020-11-11-21:48',
    index: '90',
    condition: '正在处理',
    detail: ' ',
    comment: ' '
  },
  {
    key: '3',
    coords: '(333,333)',
    time: '2020-10-10-21:48',
    index: '100',
    condition: '未处理',
    detail: ' ',
    comment: ' '
  }
]
const columns = [
  {
    title: '序列号',
    dataIndex: 'key',
    key: 'key'
  },
  {
    title: '报警点坐标',
    dataIndex: 'coords',
    key: 'coords'
  },
  {
    title: '报警时间',
    dataIndex: 'time',
    key: 'time'
  },
  {
    title: '风险指数值',
    dataIndex: 'index',
    key: 'index'
  },
  {
    title: '处理状态',
    dataIndex: 'condition',
    key: 'condition'
  },
  {
    title: '详情',
    dataIndex: 'detail',
    key: 'detail'
  },
  {
    title: '备注',
    dataIndex: 'comment',
    key: 'comment'
  }
]
function onChange (pagination, filters, sorter) {
  console.log('params', pagination, filters, sorter)
}
export default {
  data () {
    return {
      visible: false,
      viewable: false,
      dataSource,
      alarmPoint,
      columns
    }
  },
  methods: {
    onChange,
    showTable (record) {
      this.viewable = false
      this.visible = !this.visible
    },
    jumpToTable (record) {
      this.viewable = true
      this.visible = false
    }
  },
  name: 'HistoricalAlarmPoint',
  components: { UserLayout }
}
</script>
