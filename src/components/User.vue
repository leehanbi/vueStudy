<template>
  <div class="blue lighten-3 pa-3">
    <h1>User 컴포넌트</h1>
    <p>이름: {{name}}</p>
    <p>성: {{familyName}}</p>
      <v-btn color="info" @click="changeName()">이름 바꾸기</v-btn>
    <hr>
    <v-layout row wrap>
      <v-flex xs12 sm6>
        <UserDetail :nameOfChild="name"></UserDetail>
      </v-flex>
      <v-flex xs12 sm6>
        <UserEdit></UserEdit>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import UserDetail from "./UserDetail.vue"
import UserEdit from "./UserEdit.vue"

//프롭스 : 부모 컴포넌트에서 자식 컴포넌트로 값을 전달하는 방법 
// v-bind (:자식변수 = "어떤값을 줄 것인가(부모 컴포넌트) ")
export default {
  components: {
    UserDetail,
    UserEdit
  },
  data(){
    return{
      name:'마이클',
      familyName: '숀'
    }
  },
  methods: {
    changeName (){
      if(this.name == "hoza"){
        this.name ="마이클"
        this.familyName ="숀"
      }else{
        this.name = "hoza"
        this.familyName ="Jack"
      }
    
    }
  }
}
</script>