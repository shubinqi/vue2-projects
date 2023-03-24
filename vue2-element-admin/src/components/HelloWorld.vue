<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a
        href="https://cli.vuejs.org"
        target="_blank"
        rel="noopener"
      >vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel"
          target="_blank"
          rel="noopener"
        >babel</a></li>
      <li><a
          href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint"
          target="_blank"
          rel="noopener"
        >eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a
          href="https://vuejs.org"
          target="_blank"
          rel="noopener"
        >Core Docs</a></li>
      <li><a
          href="https://forum.vuejs.org"
          target="_blank"
          rel="noopener"
        >Forum</a></li>
      <li><a
          href="https://chat.vuejs.org"
          target="_blank"
          rel="noopener"
        >Community Chat</a></li>
      <li><a
          href="https://twitter.com/vuejs"
          target="_blank"
          rel="noopener"
        >Twitter</a></li>
      <li><a
          href="https://news.vuejs.org"
          target="_blank"
          rel="noopener"
        >News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a
          href="https://router.vuejs.org"
          target="_blank"
          rel="noopener"
        >vue-router</a></li>
      <li><a
          href="https://vuex.vuejs.org"
          target="_blank"
          rel="noopener"
        >vuex</a></li>
      <li><a
          href="https://github.com/vuejs/vue-devtools#vue-devtools"
          target="_blank"
          rel="noopener"
        >vue-devtools</a></li>
      <li><a
          href="https://vue-loader.vuejs.org"
          target="_blank"
          rel="noopener"
        >vue-loader</a></li>
      <li><a
          href="https://github.com/vuejs/awesome-vue"
          target="_blank"
          rel="noopener"
        >awesome-vue</a></li>
    </ul>
    <el-table
      :data="tableData"
      height="500"
      :max-height="500"
      :header-cell-style="{background:'#f5f7fa', color: '#909399'}"
      :row-style="{height:'50px'}"
      @scroll.native="handleScroll"
      ref="fixedTable"
    >
      <el-table-column
        type="index"
        width="55"
        label="序号"
      ></el-table-column>
      <el-table-column
        prop="name"
        label="姓名"
        width="180"
      ></el-table-column>
      <el-table-column
        prop="age"
        label="年龄"
        width="150"
      ></el-table-column>
      <el-table-column
        prop="gender"
        label="性别"
        width="120"
        fixed="left"
      ></el-table-column>
      <el-table-column
        prop="address"
        label="地址"
        width="320"
      ></el-table-column>
      <el-table-column
        prop="phone"
        label="电话"
        width="180"
      ></el-table-column>
      <el-table-column
        prop="email"
        label="邮箱"
        width="320"
      ></el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '123',
      tableData: [
        {
          name: "张三",
          age: 18,
          gender: "男",
          address: "北京市海淀区",
          phone: "18888888888",
          email: "zhangsan@example.com",
        },
        {
          name: "李四",
          age: 22,
          gender: "女",
          address: "上海市徐汇区",
          phone: "19999999999",
          email: "lisi@example.com",
        },
        {
          name: "王五",
          age: 30,
          gender: "男",
          address: "广州市天河区",
          phone: "17777777777",
          email: "wangwu@example.com",
        },
        {
          name: "赵六",
          age: 26,
          gender: "女",
          address: "深圳市福田区",
          phone: "16666666666",
          email: "zhaoliu@example",
        },
        {
          name: "钱七6",
          age: 24,
          gender: "男",
          address: "成都市武侯区",
          phone: "15555555555",
          email: "qianqi@example.com",
        },
        {
          name: "钱七5",
          age: 24,
          gender: "男",
          address: "成都市武侯区",
          phone: "15555555555",
          email: "qianqi@example.com",
        },
        {
          name: "钱七4",
          age: 24,
          gender: "男",
          address: "成都市武侯区",
          phone: "15555555555",
          email: "qianqi@example.com",
        },
        {
          name: "钱七3",
          age: 24,
          gender: "男",
          address: "成都市武侯区",
          phone: "15555555555",
          email: "qianqi@example.com",
        },
        {
          name: "钱七2",
          age: 24,
          gender: "男",
          address: "成都市武侯区",
          phone: "15555555555",
          email: "qianqi@example.com",
        },
        {
          name: "钱七1",
          age: 24,
          gender: "男",
          address: "成都市武侯区",
          phone: "15555555555",
          email: "qianqi@example.com",
        },
      ],
      fixedColumn: null,
    }
  },
  mounted () {
    this.$nextTick(() => {
      const tableEl = this.$refs.fixedTable.$el.querySelector('.el-table__body-wrapper')
      tableEl.addEventListener('scroll', this.handleScroll)
    })
  },
  methods: {
    handleScroll () {
      const tableEl = this.$refs.fixedTable.$el.querySelector('.el-table__body-wrapper')
      const fixedCols = this.$refs.fixedTable.columns.filter(col => col.fixed === 'left')
      const fixedWidth = fixedCols.reduce((total, col) => total + col.width, 0)
      if (tableEl.scrollLeft >= fixedWidth) {
        fixedCols.forEach(col => {
          col.fixed = false
        })
      } else {
        fixedCols.forEach(col => {
          col.fixed = 'left'
        })
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.sticky-table {
  position: relative;
}

.sticky-table .el-table__header-wrapper {
  position: sticky;
  top: 0;
  z-index: 1;
}

.sticky-table .el-table__fixed {
  position: sticky;
  left: 0;
  z-index: 1;
}

.sticky-table .el-table__fixed-right {
  position: sticky;
  right: 0;
  z-index: 1;
}

.table-container {
  height: 400px; /*设置表格容器的高度*/
  overflow: auto; /*启用滚动条*/
}
</style>
