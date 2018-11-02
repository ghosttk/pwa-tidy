<template>
  <div>
    fdsi
    <Modal @close="onCloseDialog('mShow')" :show='mShow'>
      <div slot="header"> AddPlace </div>
      <div slot="body">
        <input value="" type="text"></input>
      </div>
      <div slot="footer"> footer</div>
    </Modal>
  </div>
</template>
<script>
import Modal from './Modal'
export default {
  components: {
    Modal
  },
    onShowAddPlace: function () {
      this.mShow = true
    },
    onCloseDialog: function (wShow) {
      this[wShow] = false
    }
}
</script>
<style>

</style>
