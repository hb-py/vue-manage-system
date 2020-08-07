<template>
  <div class="manage">
    <div class="manage_header">
      <CommonForm></CommonForm>
    </div>
    <div class="manage_content">
      <CommonTable></CommonTable>
    </div>
  </div>
</template>

<script>
import CommonForm from '../../components/CommonForm'
import CommonTable from '../../components/CommonTable'
export default {
  components: {
    CommonForm,
    CommonTable
  }
}
</script>

<style lang="scss" scoped>
@import '~@/assets/scss/common';
</style>
