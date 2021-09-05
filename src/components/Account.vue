<template>
  <h2>Tipo de cuenta: {{ accountType }}</h2>
  <h2>Cuenta: {{ state ? 'Activa' : 'Desactivada' }}</h2>
  <h2>Saldo :{{ balance }}</h2>
  <div v-for="(service,index) in services" :key="index">
    {{ index + 1 }} - {{ service }}
  </div>
  <BalanceAction
      text="Aumentar Saldo"
      @action="increase"
  />
  <BalanceAction
      text="Disminuir Saldo"
      @action="decrease"
      :disabled="disabled"
  />
</template>

<script>
import BalanceAction from "@/components/BalanceAction";

export default {
  components: {
    BalanceAction
  },
  name: "Account",
  data() {
    return {
      balance: 10000,
      accountType: 'Visa',
      state: true,
      services: ['Pagos', 'Abonos', 'Transferencias'],
      disabled: false
    }
  },
  methods: {
    increase() {
      this.balance += 1000
      this.disabled = false
    },
    decrease() {
      if (this.balance === 0) {
        this.disabled = true;
        alert('Salgo Agotado');
      } else
        this.balance -= 1000
    }
  }
}
</script>

<style scoped>

</style>