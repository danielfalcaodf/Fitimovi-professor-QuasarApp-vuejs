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
  <div class="card">
     <q-card class="my-card">
      <q-card-section>
        <div class="text-h6" style="padding-bottom: 20px;">Dados Bancarios</div>
        <div class="dados-banco">
          <div class="row">
            <div class="col-6">
          <q-select color="green-14" borderless v-model="banco" :options="optionsBanco" label="Banco:" >
            <template v-if="banco" v-slot:append>
              <q-icon name="cancel" @click.stop="banco = null" class="cursor-pointer" />
              </template>
             </q-select>
          </div>
          <div class="col-6">
         <q-input color="green-14" stack-label v-model="number" prefix="Agência:" mask="#### "></q-input>
         </div>
          <div class="col-12 text-center">
         <q-input color="green-14" stack-label v-model="contaNum" label="Numero da conta:" mask="########-# "></q-input>
         </div>
          </div>
          </div>
      </q-card-section>
         <q-separator inset />
        <q-card-section>
        <div class="dados-pessoal">
          <div class=" row items-center">
            <div class="col-4">
              <div class="text-h6 " style="font-size: 18px;" color="green-14">Conta:</div>
            </div>
            <div class="col-8">
              <div class="select-col">
              <q-select color="green-14"   rounded outlined v-model="conta" :options="optionsConta" >
               <template v-if="conta" v-slot:append>
              <q-icon name="cancel" @click.stop="conta = null" class="cursor-pointer" />
              </template>
             </q-select>
              </div>
            </div>
            <div class="col-4">
              <div class="text-h6" style="font-size: 18px;">Pessoa:</div>
            </div>
            <div class="col-8">
               <div class="select-col">
             <q-select color="green-14" rounded outlined v-model="pessoa" :options="optionsPessoa" >
              <template v-if="pessoa" v-slot:append>
              <q-icon name="cancel" @click.stop="pessoa = null" class="cursor-pointer" />
              </template>
             </q-select>
               </div>
            </div>
             <div class="col-4">
              <div class="text-h6" style="font-size: 18px;">CPF</div>
            </div>
            <div class="col-8">
               <q-input
          color="green-14"
        v-model="cpf"
        label="CPF"
        mask="###.###.###-##"
      placeholder="000.000.000-00"
      />
            </div>
          </div>
        </div>
      </q-card-section>
    </q-card>
    </div>
    <div class="card">
     <q-card class="my-card">
      <q-card-section>
         <div class="text-h6" style="padding-bottom: 10px;">Transferências</div>
         <div class="row">
           <div class="col-7">
          <div class="text-h6" style="font-size: 15px;">Saldo conta FitiMovi:</div>
           </div>
           <div class="col-5">
          <div class="text-h6" style="font-size: 19px; color:  black;">{{saldo}}</div>
           </div>
           <div class="col-12 text-center">
             <q-btn color='green'><div>TRANSFERIR PARA SUA CONTA BANCARIA </div></q-btn>
           </div>
         </div>
      </q-card-section>
     </q-card>
    </div>
    <div class="card">
    <q-card class="my-card">
      <q-card-section>
        <div class="text-h6">Histórico</div>
          <div class="row">
            <div class="col-2">{{data}}</div>
            <div class="col-12 text-center  ">
              <q-btn flat color="green-14"  style="font-size: 12px;" label="Toque para receber o histórico completo Via E-mail"></q-btn>
            </div>
          </div>
      </q-card-section>
    </q-card>
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
    return {
      cpf: '',
      saldo: 'R$ 100,00',
      data: '10/10/2019',
      number: '',
      contaNum: '',
      conta: 'Conta Corrente',
      banco: 'Brasil',
      pessoa: 'Fisica',
      optionsBanco: [
        'Brasil', 'Itaú', 'Santander', 'Caixa Econômica Federal', 'Banco Bradesco'
      ],
      optionsConta: [
        'Conta Corrente', 'Conta Poupança'
      ],
      optionsPessoa: [
        'Física', 'Juridica'
      ]
    }
  },
  methods: {
  }
}
</script>
