<template>
  <div>
    <!-- 查询按钮和文本框 -->
    <!-- slot="append/ prepend"  搜索按钮的位置 -->
    <el-row :gutter="20">
      <el-col :span="8">
        <el-input placeholder="请输入内容" v-model="input5">
          <el-button @click="startQuery" slot="append" icon="el-icon-search"></el-button>
        </el-input>
      </el-col>
      <el-col :span="3">
        <el-button @click="add">新建货物存放</el-button>
      </el-col>
    </el-row>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="hw" label="货物"></el-table-column>
      <el-table-column prop="num" label="库存数量"></el-table-column>
      <el-table-column prop="wz" label="放置位置"></el-table-column>
      <el-table-column prop="min" label="库存最小值"></el-table-column>

      <el-table-column label="操作">
        <el-button size="mini" plain type="primary" icon="el-icon-edit"></el-button>
        <el-button size="mini" plain type="danger" icon="el-icon-delete"></el-button>
      </el-table-column>
    </el-table>
    <!-- 分页 -->
    <el-pagination background layout="prev, pager, next" :total="1000"></el-pagination>
    <el-dialog :visible.sync="dialogVisible" width="50%">
      <el-form label-position="left" label-width="110px" v-model="form">
        <el-form-item label="选择货物信息">
          <el-input v-model="form.xx"></el-input>
        </el-form-item>
        <el-form-item label="库存数量">
          <el-input v-model="form.sl"></el-input>
        </el-form-item>
        <el-form-item label="放置位置">
          <el-input v-model="form.wz"></el-input>
        </el-form-item>
        <el-form-item label="设置库存最小值">
          <el-input v-model="form.min"></el-input>
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
      tableData: [{ hw: 111, num: 111, wz: '点点滴滴', min: 1 }],
      dialogVisible: false,
      form: [],
      input5: ''
    }
  },
  methods: {
    handleClick () {},
    add () {
      this.dialogVisible = true
    },
    startQuery () {}
  }
}
</script>

<style>
</style>
