<template>
  <div class="red lighten-3 pa-3">
    <h3>자세한 회원 정보를 확인합니다.</h3>
    <p>{{nameOfChild}}</p>
    <p>{{sayHellow}}</p>
    <v-btn color="info" @click="switchName()">이름 바꾸기</v-btn>
  </div>
</template>


<script>
export default {
  // 부모로부터 값을 받는 props
  props:{
    // 변수 : 변수타입 
    // 기록을 해주는 이유는 데이터 타입을 알기 쉽게 위해서.
    nameOfChild:{
      type:String,
      // 반드시 필요하다는 의미
      required: true,
      // 값을 전달하지 않을 경우 디폴트값 설정 가능 
      default:'TEST'
    }
  },
  computed:{
    // 부모에게서 전달된 값을 this로 활용 가능.
    sayHellow() {
      return this.nameOfChild + '환영합니다.'
    }
  },
  methods:{
    switchName(){
      this.nameOfChild = '제라드'
    }
  },
  data(){
    return{
    }
  }
}
</script>
