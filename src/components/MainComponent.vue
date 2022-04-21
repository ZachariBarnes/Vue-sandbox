<script setup lang="ts">
import WalletFormComponent from "./Forms/WalletFormComponent.vue";
const props = defineProps<{
  isAuthorized: boolean;
  emailAddress: string;
}>();
const authorized = props.isAuthorized === true;
const wallets: any[] = [
  { coin: null, address: null, isValid: false },
  { coin: null, address: 123, isValid: false },
];
const supportedCoins = ["BZE", "VDL", "ETH", "SOL", "BTCZ"];
function addWallet() {
  wallets.push({ coin: null, address: null, isValid: false });
}
</script>

<template>
  <div class="container">
    <div class="content" v-if="authorized">
      <!--If Authorized, display form-->
      <h1 class="sectionTitle">
        Enter Wallet Information Below
      </h1>
      <div v-for="(wallet, index) in wallets" :key="index">
        <div>
          <WalletFormComponent
            :wallet="wallet"
            :supportedCoins="supportedCoins"
          />
        </div>
      </div>
      <div>
        <button class="add-btn" @onClick="addWallet">➕ Add New Wallet</button>
      </div>
    </div>
    <div class="content" v-else>
      <!--    If not authorized content block-->
      <h1>You are not Authorized to view this page.</h1>
      <h2>Please go back and pay for a token</h2>
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
  height: 44pc;
  width: 90vw;
  margin-top: 2.5rem;
  margin-bottom: 2.5rem;
}

.content {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
  padding: 0.05rem;
}

.sectionTitle {
  padding: 1rem;
  font-size: xx-large;
  text-align: center;
}
</style>
