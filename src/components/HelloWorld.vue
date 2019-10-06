
 
Pull requests
Issues
Marketplace
Explore
 
@sskrtt 
Code  Issues 0  Pull requests 0  Projects 0  Wiki  Security  Pulse  Community
Branch: master 
my-vue-practice/src/components/HelloWorld.vue
Find file Copy path
@sskrtt sskrtt 10/6の進捗 永田レビュー用
0766d4a 21 minutes ago
1 contributor
63 lines (58 sloc)  2.05 KB
RawBlameHistory
    
<template>
  <div>
    {{ msg }}
    <button v-on:click="addGuest()">ADD Guest</button>
    <button>Remove Guests</button> 
    <form>
      <p>新しいguestの情報を入力して ADD Guestボタンを押してください
      <p>name: <input type="text" v-model="newName"> name of guest: {{newName}}</p>
      <p>sex: <input type="text" v-model="newSex"> sex of guest: {{newSex}}</p>
      <p>room: <input type="number" v-model="newRoom"> room of guest: {{newRoom}}</p>
    </form>
 <div class="guest-list">
      <label class="guest-list__item"
             v-for="guest in guests">
        <p>
        <input type="checkbox">
        <button>EDIT</button>
        名前は{{ guest.name }}、 性別は {{guest.sex}}、 RoomNumberは {{guest.room}}です。
        </p>
      </label>
    </div>  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      guests : [
        {name : 'John', sex: `male`,room:150},
        {name : 'Mary', sex: `female`,room:153},
        {name : 'Ryo', sex: `male`,room:165},
      ],
    newName:"",
    newSex:"",
    newRoom:""
    }
  },
  methods:{
    addGuest:function(event){
      let checkName = this.newName && this.newName.trim();
      let checkSex = this.newSex && this.newSex.trim();
      let checkRoom = this.newRoom && this.newRoom.trim();
      if(!checkName || !checkSex || !checkRoom){
        alert `入力されていない項目があります`;
      }
      else{
        this.guests.push({
          name:this.newName,
          sex:this.newSex,
          room:this.newRoom
        })
        this.newName = "",
        this.newSex = "",
        this.newRoom = ""
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
</style>
© 2019 GitHub, Inc.
Terms
Privacy
Security
Status
Help
Contact GitHub
Pricing
API
Training
Blog
About
