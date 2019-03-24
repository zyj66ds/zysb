<template>
  <div>
    <el-tabs @tab-click="handleClick">
      <el-tab-pane label="全部物料" name="all"></el-tab-pane>
      <el-tab-pane label="零部件" name="unpaid"></el-tab-pane>
      <el-tab-pane label="原材料" name="receiving"></el-tab-pane>
    </el-tabs>
    <el-button @click="add">新建物料信息</el-button>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="lx" label="物料类型"></el-table-column>
      <el-table-column prop="mc" label="物料名称"></el-table-column>
      <el-table-column label="操作">
        <el-button size="mini" plain type="primary" icon="el-icon-edit"></el-button>
        <el-button size="mini" plain type="danger" icon="el-icon-delete"></el-button>
      </el-table-column>
    </el-table>
    <!-- 分页 -->
    <el-pagination background layout="prev, pager, next" :total="1000"></el-pagination>
    <el-dialog :visible.sync="dialogVisible" width="50%">
      <el-form label-position="left" label-width="110px" v-model="form">
        <el-form-item label="物料类型">
          <el-input v-model="form.lx"></el-input>
        </el-form-item>
        <el-form-item label="物料名称">
          <el-input v-model="form.mc"></el-input>
        </el-form-item>
        <el-form-item label="备注">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
      </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{ lx: 1111, mc: 333 }],
      form: [],
      dialogVisible: false
    }
  },
  methods: {
    handleClick () {},
    add () {
      this.dialogVisible = true
    }
  }
}
</script>

<style>
</style>
