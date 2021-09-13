<template>
  <div class="calc">
    <div class="main">
      <input v-model="op1" class="myClass" type="number" />
      <input v-model="op2" type="number"/>
      = {{ result }}
    </div>
    <div cl ass="keyboard">
      <button @click="result = op1 + op2">+</button>
      <button @click="sub(op1, op2)">-</button>
      <button @click="div">/</button>
      <button @click="multi">*</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Calculator',
  data () {
    return {
      op1: 0,
      op2: 0,
      result: 0,
      user: {
        role: 'Admin',
        grant: {
          isAdmin: true
        }
      }
    }
  },
  methods: {
    sub (op1, op2) {
      this.result = op1 - op2
    },
    div () {
      const { op1, op2 } = this
      this.result = op1 / op2
    },
    multi () {
      const { op1, op2 } = this
      this.result = op1 * op2
    }
  }
}
</script>

<style scoped lang="scss">
.myClass {
  width: 100px;
}
</style>
