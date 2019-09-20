<template >
 <div class="q-gutter-y-md">
        <div class="img-logo text-center">
          <q-img
                src="../assets/Vector.png"
                style="width: 120px"
              >
          </q-img>
          </div>

<div class="q-pa-md row items-center  q-gutter-y-md"  >
  <div class="card" >
     <q-card class="my-card">
      <q-card-section>
        <div class="text-h6">Cadastrar Aula</div>
        <q-checkbox  class="label" v-model="AulaIndividual" label="Aula Individual" color="green-14" />
        <q-checkbox  class="label" v-model="AulaColetiva" label="Aula Coletiva" color="green-14" />
         <q-select class="label" color="green-14" rounded outlined v-model="modalidade" :options="optionsmodalidade" label="Modalidade: " ></q-select>
      </q-card-section>
    </q-card>
    </div>
      <div class="card" >
     <q-card class="my-card">
      <q-card-section>
        <div class="text-h6">Valor da Aula</div>
          <q-slider v-model="standard" :min="0" :max="50" color="green-14"/>
          <q-separator inset />
          <div class=" column items-end ">
            <div class="col-12 self-end">
              <div class="text-h6">R$ 100,00</div>
            </div>
          </div>
          <div class="column items-end">
              <div class="col-12 self-end">
                  <div class="text-h6 text-valor">Valor mínimo por hora/aula</div>
            </div>
          </div>
      </q-card-section>
    </q-card>
    </div>
       <div class="card" >
     <q-card class="my-card">
      <q-card-section>
        <div class="text-h6">Adicione as informações da aula </div>
         <q-input color="green-14" placeholder="Toque para inserir o local" rounded outlined bottom-slots v-model="local"  >
        <template v-slot:append>
          <q-btn color=green-14 round dense flat icon="place" @click="local = ''" class="cursor-pointer"  />
        </template>
      </q-input>
 <q-input rounded outlined bottom-slots color=green-14 v-model="date" >
      <template v-slot:append>
        <q-icon color=green-14 name="event" class="cursor-pointer">
          <q-popup-proxy ref="qDateProxy" transition-show="scale" transition-hide="scale">
            <q-date mask="DD/MM/YYYY" color=green-14 v-model="date" @input="() => $refs.qDateProxy.hide()" />
          </q-popup-proxy>
        </q-icon>
      </template>
    </q-input>
    <q-input rounded outlined bottom-slots color=green-14 v-model="hora">
      <template v-slot:append>
        <q-icon color=green-14 name="access_time" class="cursor-pointer">
          <q-popup-proxy transition-show="scale" transition-hide="scale">
            <q-time color=green-14 v-model="hora" mask="HH:mm" format24h @input="() => $refs.qDateProxy.hide()" />
          </q-popup-proxy>
        </q-icon>
      </template>
    </q-input>
      </q-card-section>
    </q-card>
    </div>
     <div class="btn-ok">
  <q-btn flat round  icon="arrow_forward" class="" />
  </div>
</div>
 </div>
</template>

<style lang="stylus" scoped>
.img-logo
{
     width: 100%
    height: 120px
    margin-top: 30px
    margin-bottom: -70px;
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
.label
{
   color:  #00c853;
}
.text-valor
{
      font-size: 14px;
}
</style>

<script>
export default {
  data () {
    return { AulaIndividual: false, AulaColetiva: false, modalidade: 'Física', optionsmodalidade: ['Física', 'Juridica'], standard: 0, local: '', date: '01/01/2019', hora: '00:00' }
  },

  methods: {
  }
}
</script>
