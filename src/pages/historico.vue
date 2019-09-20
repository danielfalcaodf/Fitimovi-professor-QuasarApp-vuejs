<template >
 <div class="q-gutter-y-md">
     <div class="bg-orange text-white">
      <q-header  class="bg-green-14" elevated>
      <q-toolbar >
        <q-btn flat round dense icon="arrow_back" class="" />
        <div class="img-logo text-center">
          <q-img
                src="../assets/Vector.png"
                style="width: 100px"
              >
          </q-img>
          </div>
          <q-btn flat round dense icon="menu" class="" />
        </q-toolbar>
      </q-header>
    </div>
<div class="q-pa-md row items-center  q-gutter-y-md"  >
  <div class="text-h5"  style="">Histórico</div>
  <div class="card" v-for="historio in historios" :key="historio.id">
     <q-card class="my-card">
      <q-card-section>
        <div class="dados-banco">
          <div class="row">
            <div class="col-12">
              <div class="text-h6">Local: {{historio.local}}</div>
            </div>
            <div class="col-12">
              <div class="text-h6">Dia: {{historio.data}}</div>
            </div>
            <div class="col-12">
              <div class="text-h6">Atividade {{historio.atividade}}</div>
            </div>
          </div>
          </div>
        <div class="dados-pessoal">
          <q-separator inset />
          <div class=" column items-end ">
            <div class="col-12 self-end">
              <div class="text-h6">{{historio.saldo}}</div>
            </div>
          </div>
        </div>
      </q-card-section>
    </q-card>
    </div>
  <div class="col-12 text-center  ">
              <q-btn flat color="green-14"  style="font-size: 12px;" label="Toque para receber o histórico completo Via E-mail"></q-btn>
            </div>
</div>
 </div>
</template>

<style lang="stylus" scoped>
.img-logo
{
  width  100%
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
  color:  #00c853;
}
.text-h5
{
  color:  #00c853;
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
.card
{
      width: 100%;
}
.select-col
{
    padding-top: 10px;
    padding-bottom: 10px;
}
.q-card {
    box-shadow: 0 1px 5px #00c853, 0 2px 2px #00c853, 0 3px 1px -2px #00c853;
    border-radius: 30px;
    vertical-align: top;
    background: #fff;
    position: relative;
}
</style>

<script>
export default {
  data () {
    return { historios: [{ saldo: 'R$ 100,00', data: '10/10/2019', local: 'Jd. Portugal', atividade: 'Pilates' }] }
  },

  methods: {
  }
}
</script>
