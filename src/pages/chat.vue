<template >
 <div class="q-gutter-y-md">
    <div class="bg-black text-white">
      <q-header  class="bg-black" elevated>
      <q-toolbar >
        <q-btn flat round dense icon="arrow_back" class="" />
        <div style="width: 100%; padding: 34px;">
        <div class="status-avatar">
          <div class="nome-status">
          <div class="text-nome">Daniel Falcão</div>
          <div class="text-status">4,96 Excelente</div>
          </div>
            <q-avatar>
            <q-img
                  src="../assets/daniel.jpg"
                  style="width: 100px"
                >
            </q-img>
            </q-avatar>
          </div>
        </div>
        </q-toolbar>
      </q-header>
    </div>
<div class="q-pa-md row items-center  q-gutter-y-md"  >
  <div class="chat" >
      <q-scroll-area style="height: auto;">
       <q-chat-message
        name="Daniel"
        avatar="../assets/daniel.jpg"
        :text="[  'Estou aguardando!']"
        stamp="1 minutes ago"
        size="6"
        text-color="white"
        bg-color="blue-grey-6"
      />
            <q-chat-message
        name="Jane"
        avatar="https://cdn.quasar.dev/img/avatar5.jpg"
        :text="[  'Estou a caminho...']"
        stamp="1 minutes ago"
        size="6"
        sent
        text-color="white"
        bg-color="green-14"
      />
         </q-scroll-area >
  </div>
  <div class="send-msg">
    <q-input color='green-14'  placeholder='Digita aqui...' rounded outlined v-model="chat">
        <template v-slot:before>
          <q-avatar>
            <img src="https://cdn.quasar.dev/img/avatar5.jpg">
          </q-avatar>
        </template>
       <template v-slot:hint>
          Field hint
        </template>
        <template v-slot:after>
          <q-btn  color='green-14' round dense flat icon="send" />
        </template>
      </q-input>
  </div>
</div>
 </div>
</template>

<style lang="stylus" scoped>
.img-logo
{
  width  100%
  margin-right: 32px
  padding: 10px;

}
.icon-conta
{
      margin-top: 0px
  font-size: 40px
  width 100%;
}
.form-cad
{
      margin-top: 0px
      width: 100%;
}
.input
{
  padding  10px
}
.btn-ok{
  width 100%
  position: relative
  left: 85%;

}
.text-h6
{
  width 100%
}
.status-avatar
{
    display: inline-flex
    position: absolute
    right: 10px
    top: 7px;
}
.text-nome
{
     font-size: 18px
    padding-right: 10px;
}
.text-status
{
    font-size: 14px
}
.q-toolbar .q-avatar {
    font-size: 55px
}
.chat{
  width 100%

  margin-bottom: 46px;
}
.send-msg
{
    width: 100%;
    position: fixed;
    bottom: -3px;
    left: 3px;
    padding: 6px;
    z-index 999;
        background-color: white;

}
</style>

<script>
export default {
  data () {
    return {
      text: '',
      chat: '',
      items: [{}, {}, {}, {}, {}, {}, {}]
    }
  },
  methods: {
  }
}
</script>
