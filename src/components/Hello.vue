<template>
  <div class="hello">
    <AddPlaceDialog @onAddPlace="onAddPlace" @onCloseDialog="onClose('mShowAddPlace')" :mShow="mShowAddPlace"></AddPlaceDialog>
    <AddItemDialog @onAddItem="onAddItem" @onCloseDialog="onClose('mShowAddItem')" :mShow="mShowAddItem"></AddItemDialog>
    <button @click="onShowAddPlace">AddPlace</button>
    <div v-for="(pl, pi) in tdata"> {{ pl.place }} 
      <button v-for="item in pl.items"> {{ item }} </button>
      <button @click="onShowAddItem(pi)"> AddItem </button>
    </div>
  </div>
</template>

<script>
import AddPlaceDialog from './AddPlaceDialog'
import AddItemDialog from './AddItemDialog'
export default {
  name: 'hello',
  components: {
    AddPlaceDialog,
    AddItemDialog
  },
  data () {
    return {
      tdata: '',
      isShowLog: false,
      mShowAddPlace: false,
      mShowAddItem: false,
      curPlaceIndex: 0
    }
  },
  mounted: function () {
    var mydate = new Date()
    this.tdata = [{place: '01', items: ['01'], dates: [mydate.toLocaleString()], unsaved: [true]}]
  },
  methods: {
    onAddItem: function (iname) {
      var mydate = new Date()
      this.tdata[this.curPlaceIndex].items.push(iname)
      this.tdata[this.curPlaceIndex].dates.push(mydate)
      this.tdata[this.curPlaceIndex].unsaved.push(true)
    },
    onShowAddItem: function (pplace) {
      this.curPlaceIndex = pplace
      this.mShowAddItem = true
    },
    onShowAddPlace: function () {
      this.mShowAddPlace = true
    },
    onClose: function (wShow) {
      this[wShow] = false
    },
    onAddPlace: function (pname) {
      var mydate = new Date()
      this.tdata.push({place: pname, items: ['01'], dates: [mydate.toLocaleString()], unsaved: [true]})
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #35495E;
}
</style>
