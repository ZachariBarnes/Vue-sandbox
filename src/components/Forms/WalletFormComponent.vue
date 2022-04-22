<script setup lang="ts">
/* eslint-disable vue/no-mutating-props */
const props = defineProps<{
  wallet: any;
  supportedCoins: string[];
}>();
const validAddress = props.wallet.address != null;
// const selectedCoin = props.wallet.coin;
</script>

<template>
  <div class="content">
    <div class="form">
      <table>
        <tr>
          <td>
            <select class="dropdown" :v-model="props.wallet.coin">
              <option
                v-for="(option, index) in props.supportedCoins"
                :value="option"
                :key="option + index"
              >
                {{ option }}
              </option>
            </select>
          </td>
          <input
            class="inputBox"
            v-model="props.wallet.address"
            placeholder="Input Wallet Address for Coin :"
          />
          <td>
            <p class="label" v-if="validAddress">Valid Address</p>
            <p class="error-label" v-else>Invalid Address</p>
          </td>
          <td>
            <button class="btn">Validate address</button>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: space-around;
  align-items: flex-start;
  border-bottom: 2px solid hsla(160, 100%, 37%, 1);
  background-color: #131313 !important;
}

.content {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
  padding: 1rem;
}

.form {
  color: #ddd;
  background-color: #212124;
  border-radius: 3px;
  margin: 1rem;
  padding: 1.5rem !important;
  min-width: 50vw;
  max-width: 90vw;
  justify-content: space-around;
  align-items: flex-start;
  box-shadow: 0 4px 8px 0 rgb(0 0 0 / 20%);
  transition: all 0s cubic-bezier(0.685, 0.0473, 0.346, 1);
  box-sizing: border-box;
  vertical-align: inherit;
  border-color: inherit;
  text-align: left;
  font-size: 0.9rem;
  max-height: 20px;
  display: table;
  text-indent: initial;
  border-spacing: 2px;
}
.error-label {
  text-decoration: none;
  color: hsla(0, 100%, 50%);
  transition: 0.4s;
  padding: 1rem;
  font-size: large;
}
.label {
  transition: 0.4s;
  padding: 1rem;
  font-size: large;
}
</style>
