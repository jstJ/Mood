<template>
  <el-date-picker
    v-model="value"
    type="datetime"
    value-format="yyyy/MM/dd HH:mm"
    placeholder="选择日期时间"
  >
  </el-date-picker>
</template>

<script>
export default {
  props: ["originalDate"],
  data() {
    return {
      value: "",
    };
  },
  watch: {
    value(val) {
      this.$emit("getDate", val);
    },
  },
  mounted() {
    // 默认时间
    if (this.originalDate && JSON.stringify(this.originalDate) != "{}") {
      this.value = this.originalDate;
    }
  },
};
</script>