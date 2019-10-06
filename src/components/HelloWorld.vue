<template>
  <div>
    {{ msg }}
    <form>
      <button v-on:click="addGuest()">ADD Guest</button>
      <button>Remove Guests</button>
      <p>新しいguestの情報を入力して ADD Guestボタンを押してください
      <p>name: <input type="text" v-model="newName"> name of guest: {{newName}}</p>
      <p>sex: <input type="text" v-model="newSex"> sex of guest: {{newSex}}</p>
      <p>room: <input type="number" v-model="newRoom"> room of guest: {{newRoom}}</p>
    </form>
 <div class="guest-list">
      <label class="guest-list__item"
             v-for="guest in guests">
        <p>
        <input type="checkbox">
        <button>EDIT</button>
        名前は{{ guest.name }}、 性別は {{guest.sex}}、 RoomNumberは {{guest.room}}です。
        </p>
      </label>
    </div>  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      guests : [
        {name : 'John', sex: `male`,room:150},
        {name : 'Mary', sex: `female`,room:153},
        {name : 'Ryo', sex: `male`,room:165},
      ],
    newName:"",
    newSex:"",
    newRoom:""
    }
  },
  methods:{
    addGuest:function(event){
      let checkName = this.newName && this.newName.trim();
      let checkSex = this.newSex && this.newSex.trim();
      let checkRoom = this.newRoom && this.newRoom.trim();

      if(!checkName & !checkSex & !checkRoom){
        alert `入力されていない項目があります`;
      }
      this.guests.push({
        name:newName,
        sex:newSex,
        room:newRoom
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

</style>
