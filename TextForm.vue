<template>
  <el-form :model="form">
      <div v-for="(item,index) in form.addForm" :key="`addForm${index}`">
          <el-col :span="2">
              <el-form-item label="" :prop="`addForm.${index}.name`">
                  <el-input v-model="item.name" />
              </el-form-item>
          </el-col>
          <el-col :span="2">
              <el-form-item label="" :prop="`addForm.${index}.age`">
                  <el-input v-model="item.age" />
              </el-form-item>
          </el-col>
          <el-col :span="1"></el-col>
          <el-col :span="1">
            <el-button  @click='deleteCol(index)'>-</el-button>
          </el-col>
          <el-col :span="1">
            <el-button  @click='addCol'>+</el-button>
        </el-col>
      </div>
  </el-form>
</template>

<script>
export default {
  name: 'TextForm',
  data(){
     return {
         form: {
            addForm : [
                {
                    name: '',
                    age: 0,
                }
            ]
          }
      }
  },
  methods:{
    deleteCol(idex){
      if(this.form.addForm.length === 1){
          return alert('提示：必须填写一条')
      } 
      this.form.addForm.splice(idex,1)
    },
    addCol(){
      this.form.addForm.push({name: '',age:0})
    }
  }

}
</script>


