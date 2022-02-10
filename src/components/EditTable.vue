<template>
  <div>
    <table>
    <tr v-for="(item , index) in table" :key="index">
    <td>
      <button v-on:click="openModal(item)">edit</button>
      <button v-on:click="deleteCol(index)">delete</button></td>
    <td v-for="val in item" :key="val">{{ val }}</td>
    </tr>
    </table>
    
    <a :val="list" id="overlay" v-if="showContent">
        <div id="content">
          <input v-model="list[1]">
          <input v-model="list[2]">
          <button v-on:click="closeModal">Close</button>
        </div>
    </a>
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

table{
  margin-top: 30px;
  border-collapse: collapse;
  border-spacing: 0;
  width: 100%;
}

table tr{
  border-bottom: solid 1px #eee;
  cursor: pointer;
}
table tr:last-child{
  border-bottom: 0px;
  cursor: pointer;
}


table th,table td{
  text-align: center;
  width: 20%;
  padding: 15px 0;
}

button {
  display: ;
  position: relative;
  width: 80px;
  padding: 0.6em;
  margin: 3px 0px;
  text-align: center;
  text-decoration: none;
  color: #fff;
  background: #666666;
  border: 0px;
}
button:hover {
   opacity:0.8;
   cursor: pointer;
   text-decoration: none;
}

#overlay{
  /* 要素を重ねた時の順番 */
  z-index:1;

  /* 画面全体を覆う設定 */
  position:fixed;
  top:0;
  left:0;
  width:100%;
  height:100%;
  background-color:rgba(0,0,0,0.5);

  /* 画面の中央に要素を表示させる設定 */
  display: flex;
  align-items: center;
  justify-content: center;

}

#content{
  z-index:2;
  width:50%;
  padding: 1em;
  background:#fff;
}

</style>

<script>

export default {
  name: 'EditTable',
  data () {
    return {
      showContent: false,
      table: [
     ["11","12","13","14"],
     ["21","22","23","24"],
     ["31","32","33","34"],
     ["41","42","43","44"]
      ]
    }
  },
  methods: {
    openModal: function(item){ //編集モーダル開く
      this.showContent = true
      this.list = item
    },
    closeModal: function(){ //編集モーダル閉じる
      this.showContent = false
    },
    deleteCol: function(item){ //行削除
      this.table.splice(item,1)
    }
  }
}

</script>
