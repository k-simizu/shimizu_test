<template>
  <div align="center">
    <ul>
      <p> {{ sum() }}</p>
      <li v-for="item in list" :key="item"><input v-model="item.name"><input v-model="item.value"></li>
      <div style="margin-top:8px;">
        <button v-on:click="clearList">remove</button>
        <button v-on:click="addItem">add</button>
      </div>
    </ul>
  </div>
</template>

<style>
body {

  font-family: system-ui;
  background: #fffacd;
  color: #666666;
  text-align: center;
}

li {
  list-style-type:none;
}
</style>

<script>
export default {
  name: 'SumUp',
  data () {
    return {
      counter: 0,
      list: [
        {
          name:"",
          value:null
        }
      ]
    }
  },
  methods: {
  sum: function() { //合計計算
      var sum=0
      var message="sum:"
      for(let i=0; i<=this.counter; i++) {
                        if(!isNaN(this.list[i].value)){
                        sum += Number(this.list[i].value)
                      }
                      else
                      {
                      return "Please enter valid values"
                      }
                    }
      return message+sum
    },
    addItem: function() { //フォーム一行追加
      this.counter+=1
      this.list.push({
        name: "",
        value: ""
      })
    },
    clearList: function() { //フォームリセット
      this.counter=0
      this.list=[
        {
          name:"",
          value:null
        }
      ]
    }
  }
}
</script>
