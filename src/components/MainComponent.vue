<script setup lang="ts">
const props = defineProps<{
  isAuthorized: boolean;
  emailAddress: string;
}>();
const authorized = props.isAuthorized === true;
const wallets: any[] = [];
</script>

<template>
  <div class="container">
    <div class="content" v-if="authorized">
      <!--If Authorized, display form-->
      <div v-for="(wallet, index) in wallets" :key="index">
        <WalletFormComponent :wallet="wallet" />
      </div>
      <div>
        <button class="add-btn">➕ Add New Wallet </button>
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
  height: 26.65rem;
  width: 92.25vw;
}

.content {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
  padding: 1rem;
}
</style>
