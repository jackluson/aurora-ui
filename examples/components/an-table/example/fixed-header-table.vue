<template>
  <an-table :column="column" :data="data" border maxHeight="250"> </an-table>
</template>

<script>
export default {
  data() {
    return {
      column: [
        {
          prop: "date",
          label: "日期",
        },
        {
          prop: "name",
          label: "姓名",
        },
        {
          prop: "address",
          label: "地址",
        },
      ],
      data: [],
    };
  },
  created() {
    for (let i = 0; i < 20; i++) {
      this.data.push({
        date: `2016-05-${i + 1}`,
        name: `王小虎${i + 1}`,
        address: `上海市普陀区金沙江路 ${i + 1} 弄`,
      });
    }
  },
};
</script>
