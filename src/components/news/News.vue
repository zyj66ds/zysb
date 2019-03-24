<template>
  <div>
    <el-button @click="add">新建新闻</el-button>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column prop="bt" label="新闻标题"></el-table-column>
      <el-table-column prop="date" label="发布时间"></el-table-column>

      <el-table-column label="操作">
        <el-button size="mini" plain type="primary" icon="el-icon-edit"></el-button>
        <el-button size="mini" plain type="danger" icon="el-icon-delete"></el-button>
      </el-table-column>
    </el-table>
    <!-- 分页 -->
    <el-pagination background layout="prev, pager, next" :total="1000"></el-pagination>
    <el-dialog :visible.sync="dialogVisible" width="50%">
      <el-form label-position="left" label-width="110px" v-model="form">
        <el-form-item label="新闻标题">
          <el-input v-model="form.dd"></el-input>
        </el-form-item>
        <el-form-item label="新闻内容">
          <el-input v-model="form.sq"></el-input>
        </el-form-item>
        <el-form-item name="two" label="商品图片">
          <el-upload>
            <i class="el-icon-plus"></i>
          </el-upload>
        </el-form-item>
        <el-form-item label="发布时间">
          <el-input v-model="form.lx"></el-input>
        </el-form-item>
        <el-form-item label="发布人">
          <el-input v-model="form.cd"></el-input>
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
      tableData: [{ bt: '大事件', date: '11-11' }],
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
