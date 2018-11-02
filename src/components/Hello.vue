<template>
  <div class="hello">
    <AddPlaceDialog></AddPlaceDialog>
    <div v-for="pi in tdata"> {{ pi.place }} 
    <button @click="onShowAddPlace">AddPlace</button>
      <button v-for="item in pi.items"> {{ item }} </button>
    </div>
  </div>
</template>

<script>
import AddPlaceDialog from './AddPlaceDialog'
export default {
  name: 'hello',
  components: {
    AddPlaceDialog
  },
  data () {
    return {
      tdata: '',
      isShowLog: false,
      mShow: false
    }
  },
  mounted: function () {
    var mydate = new Date()
    this.tdata = [{place: '01', items: ['01'], dates: [mydate.toLocaleString()], unsaved: [true]}]
  },
  methods: {
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
