<template>
  <div class="hello">
    <modal @onCloseDialog="closeThis('isShowLog')" :is-show='isShowLog'></modal>
    <Modal :show='mShow'></Modal>
    <div v-for="pi in tdata"> {{ pi.place }} 
    <button @click="onShowAddPlace">AddPlace</button>
      <button v-for="item in pi.items"> {{ item }} </button>
    </div>
  </div>
</template>

<script>
import modal from './dialog'
import Modal from './Modal'
export default {
  name: 'hello',
  components: {
    modal,
    Modal
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
    onShowAddPlace: function () {
      this.mShow = true
    },
    onCloseDialog: function () {
      this.isShowLog = false
    },
    closeThis: function (dlg) {
      console.log(dlg)
      this.isShowLog = false
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
