<template>
  <div>
    <el-tabs @tab-click="handleClick">
      <el-tab-pane label="全部入库单" name="all"></el-tab-pane>
      <el-tab-pane label="未执行" name="unpaid"></el-tab-pane>
      <el-tab-pane label="已执行" name="receiving"></el-tab-pane>
    </el-tabs>
    <el-button @click="add">新建入库单</el-button>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="id" label="入库单id"></el-table-column>
      <el-table-column prop="date" label="入库申请时间"></el-table-column>
      <el-table-column prop="status" label="入库状态">
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
        <el-form-item label="入库物料">
          <el-input v-model="form.dd"></el-input>
        </el-form-item>
        <el-form-item label="入库原因">
          <el-input v-model="form.sq"></el-input>
        </el-form-item>
        <el-form-item label="入库申请人">
          <el-input v-model="form.gh"></el-input>
        </el-form-item>
        <el-form-item label="入库申请时间">
          <el-input v-model="form.lx"></el-input>
        </el-form-item>
        <el-form-item label="入库状态">
          <el-input v-model="form.cd"></el-input>
        </el-form-item>
        <el-form-item label="入库操作人">
          <el-input v-model="form.yf"></el-input>
        </el-form-item>
        <el-form-item label="实际入库时间">
          <el-input v-model="form.fs"></el-input>
        </el-form-item>
      </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogVisible = false">确 认</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{ id: 111, date: '11-11', status: true }],
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
