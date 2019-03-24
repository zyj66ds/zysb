<template>
  <div>
    <el-tabs @tab-click="handleClick">
      <el-tab-pane label="全部出库单" name="all"></el-tab-pane>
      <el-tab-pane label="未执行" name="unpaid"></el-tab-pane>
      <el-tab-pane label="已执行" name="receiving"></el-tab-pane>
    </el-tabs>
    <el-button @click="add">新建出库单</el-button>
    <el-table :data="outData" style="width: 100%">
      <el-table-column prop="id" label="出库单ID" width="180"></el-table-column>
      <el-table-column prop="outTime" label="出库申请时间" width="180"></el-table-column>
      <el-table-column prop="outStatus" label="出库状态">
        <template slot-scope="scope">
          <el-switch v-model="scope.row.outStatus"></el-switch>
        </template>
      </el-table-column>
      <el-table-column label="操作">
        <template slot-scope="scope">
          <el-button size="mini" plain type="primary" icon="el-icon-edit"></el-button>
          <el-button size="mini" plain type="danger" icon="el-icon-delete"></el-button>
        </template>
      </el-table-column>
    </el-table>
    <!-- 分页 -->
    <el-pagination background layout="prev, pager, next" :total="1000"></el-pagination>

    <!-- 表单域 -->
    <el-dialog :visible.sync="dialogVisible" width="50%">
      <el-form label-position="left" label-width="110px" v-model="form">
        <el-form-item label="出库货物">
          <el-input v-model="form.hw"></el-input>
        </el-form-item>
        <el-form-item label="出库原因">
          <el-input v-model="form.yy"></el-input>
        </el-form-item>
        <el-form-item label="出库申请人">
          <el-input v-model="form.whichone"></el-input>
        </el-form-item>
        <el-form-item label="出库申请时间">
          <el-input v-model="form.sj"></el-input>
        </el-form-item>
        <el-form-item label="出库状态">
          <el-input v-model="form.status"></el-input>
        </el-form-item>
        <el-form-item label="出库操作人">
          <el-input v-model="form.cz"></el-input>
        </el-form-item>
        <el-form-item label="实际出库时间">
          <el-input v-model="form.cktime"></el-input>
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
      outData: [{ id: 12123, outTime: '1993-12-31', outStatus: false }],
      dialogVisible: false,
      form: []
    }
  },
  methods: {
    add () {
      this.dialogVisible = true
    },
    handleClick (res) {
      console.log(res)
    }
  }
}
</script>

<style>
</style>
