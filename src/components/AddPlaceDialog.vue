<template>
    <Modal @close="onClose('mShow')" :show='mShow'>
      <div slot="header"> AddPlace </div>
      <div slot="body">
        <input placeholder="place name" @keyup.enter="AddPlace" v-model="placeName" type="text"></input>
      </div>
      <div slot="footer"> footer</div>
    </Modal>
</template>
<script>
import Modal from './Modal'
export default {
  props: ['mShow'],
  data () {
    return {
      placeName: ''
    }
  },
  components: {
    Modal
  },
  methods: {
    onShowAddPlace: function () {
      this.mShow = true
    },
    onClose: function (wShow) {
      this.$emit('onCloseDialog')
    },
    AddPlace: function () {
      this.$emit('onAddPlace', this.placeName)
      this.onClose()
    }
  }
}
</script>
<style>

</style>
