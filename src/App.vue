<template>
  <div class="container">
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLNavigator.open?id=CDCLGFR0100MM01&param={\'PLAY\'}')">운세</button>
      <span class="url-text">shlic://SHLNavigator.open?id=CDCLGFR0100MM01 param={\'PLAY\'}"</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('https://example.com/page2')">Button 2</button>
      <span class="url-text">https://example.com/page2</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('https://example.com/page3')">Button 3</button>
      <span class="url-text">https://example.com/page3</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('https://example.com/page4')">Button 4</button>
      <span class="url-text">https://example.com/page4</span>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    navigateTo(url) {
      window.location.href = url;
    }
  }
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 100vh;
}

.button-row {
  display: flex;
  align-items: center;
  margin: 10px 0;
}

.btn {
  margin-right: 15px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f0f0f0;
  transition: background-color 0.2s ease;
}

.btn:hover {
  background-color: #e0e0e0;
}

.url-text {
  font-size: 14px;
  color: #555;
}
</style>