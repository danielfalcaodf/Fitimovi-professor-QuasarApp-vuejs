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
        </q-toolbar>
      </q-header>
    </div>
<div class="q-pa-md row items-center  q-gutter-y-md"  >

  <div class="text-h6 text-center ">
  Vamos iniciar o seu cadastro!
  </div>
  <div class="icon-conta  text-center ">
    <q-icon  name="perm_contact_calendar"></q-icon>
  </div>
  <div class="form-cad text-center">
    <div class="row items-center">
  <div class="col-6">
    <div class="input">
      <q-input color="green" v-model="nome" label="Nome"  />
    </div>
    </div>
     <div class="col-6">
  <div class="input">
     <q-input color="green" v-model="sobrenome" label="Sobrenome"  />
  </div>
     </div>
  </div>
    <div class="row items-center">
      <div class="col-6">
  <div class="input">
    <q-input  color="green" v-model="date"  type="date" stack-label  label="Data de Nascimento "  />
  </div>
  </div>
  <div class="col-6">
    <div class="input">
      <q-input
        v-model="phone"
        color="green"
        label="Celular"
        mask="(##) ##### - ####"
        placeholder="(00) 00000 - 0000"
      />
  </div>
  </div>
    </div>
    <div class="row">
      <div class="col-12">
        <div class="input">
            <q-input color="green" v-model="email" type="email" label="Email"  />
        </div>
      </div>
  </div>
      <div class="row">
      <div class="col-12">
        <div class="input">
           <q-input
          color="green"
        v-model="cpf"
        label="CPF"
        mask="###.###.###-##"
      placeholder="000.000.000-00"
      />
        </div>
      </div>
  </div>
      <div class="row">
      <div class="col-12">
        <div class="input">
        <q-input
            color="green"
            v-model="cnpj"
            label="CNPJ (Opicional)"
            mask="##.###.###/####-##"
            placeholder="00.000.000/0000-00"
      />
        </div>
      </div>
  </div>
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

</style>

<script>
export default {
  data () {
    return {
      text: '',
      nome: '',
      sobrenome: '',
      date: '',
      phone: '',
      cpf: '',
      email: '',
      cnpj: ''
    }
  }
}
</script>
