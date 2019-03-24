<template>
  <div>
    <el-tabs @tab-click="handleClick">
      <el-tab-pane label="全部物料" name="all"></el-tab-pane>
      <el-tab-pane label="零部件" name="unpaid"></el-tab-pane>
      <el-tab-pane label="原材料" name="receiving"></el-tab-pane>
    </el-tabs>
    <el-button @click="add">新建物料信息</el-button>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="id" label="采购申请id"></el-table-column>
      <el-table-column prop="time" label="采购申请时间"></el-table-column>
      <el-table-column prop="status" label="申请状态">
        <template slot-scope="scope">
          <el-switch v-model="scope.row.status"></el-switch>
        </template>
      </el-table-column>

      <el-table-column label="操作">
        <el-button size="mini" plain type="primary" icon="el-icon-edit"></el-button>
        <el-button size="mini" plain type="danger" icon="el-icon-delete"></el-button>
      </el-table-column>
    </el-table>
    <!-- 分页 -->
    <el-pagination background layout="prev, pager, next" :total="1000"></el-pagination>
    <el-dialog :visible.sync="dialogVisible" width="50%">
      <el-form label-position="left" label-width="110px" v-model="form">
        <el-form-item label="选择采购物料">
          <el-input v-model="form.lx"></el-input>
        </el-form-item>
        <el-form-item label="采购数量">
          <el-input v-model="form.mc"></el-input>
        </el-form-item>
        <el-form-item label="货物单价">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
        <el-form-item label="总价">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
        <el-form-item label="申请原因">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
        <el-form-item label="申请人">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
        <el-form-item label="申请状态">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
        <el-form-item label="采购申请时间">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
        <el-form-item label="采购审批人">
          <el-input v-model="form.bz"></el-input>
        </el-form-item>
      </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">提交保存</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{ id: 111, time: '11-11', status: true }],
      dialogVisible: false,
      form: []
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
