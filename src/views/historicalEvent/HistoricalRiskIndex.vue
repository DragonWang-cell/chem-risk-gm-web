<template>
  <page-header-wrapper>
    <a-card :bordered="false">
      <div class="table-page-search-wrapper">
        <a-form layout="inline">
          <a-row :gutter="48">
            <a-col :md="8" :sm="16">
              <a-list item-layout="horizontal" :data-source="areadata">
                <a-list-item slot="renderItem" slot-scope="item">
                  <a-list-item-meta
                    description="点击显示该区域历史风险指数"
                  >
                    <a slot="title" @click="j2table">{{ item.title }}</a>
                  </a-list-item-meta>
                </a-list-item>
              </a-list>
            </a-col>
            <a-col :md="16" :sm="16">
              <a-table :columns="columns" :data-source="riskdata">
                <template v-slot:name="{ text }">
                  <a>{{ text }}</a>
                </template>
                <template v-slot:tags="{ text: details }">
                  <span>
                    <a-tag
                      v-for="details in details"
                      :key="details"
                      :color='green'
                    >
                      {{ details }}
                    </a-tag>
                  </span>
                </template>
              </a-table>
            </a-col>
          </a-row>
        </a-form>
      </div>
    </a-card>
  </page-header-wrapper>
</template>
<script>
const areadata = [
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
const riskdata = [
  {
    key: '1',
    index: '1',
    riskindex: 32,
    computetime: '2019-10-10',
    details: ['详情'],
    remarks: ['事件1']
  },
  {
    key: '2',
    index: '2',
    riskindex: 24,
    computetime: '2019-11-25',
    details: ['详情'],
    remarks: '无'
  },
  {
    key: '3',
    index: '3',
    riskindex: 64,
    computetime: '2020-02-10',
    details: ['详情'],
    remarks: '无'
  }
]
const columns = [
  {
    // dataIndex: 'name',
    title: '序列号',
    key: 'index',
    // slots: { title: 'customTitle', customRender: 'name' }
    dataIndex: 'index'
  },
  {
    title: '风险指数值',
    dataIndex: 'riskindex',
    key: 'riskindex'
  },
  {
    title: '计算时间',
    dataIndex: 'computetime',
    key: 'computetime'
  },
  {
    title: '详情',
    key: 'details',
    dataIndex: 'details',
    slots: { customRender: 'details' }
  },
  {
    title: '备注',
    key: 'remarks',
    dataIndex: 'remarks',
    slots: { customRender: 'remarks' }
  }
]
export default {
  /* components: {
    SmileOutlined,
    DownOutlined
  }, */
  data () {
    return {
      areadata,
      riskdata,
      columns
    }
  },
  methods: {
    j2table () {

    }
  }
}
</script>
<style></style>
