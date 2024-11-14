<template>
  <div class="container">
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLNavigator.open?id=CDCLGFR0100MM01&param={\'PLAY\'}')">운세</button>
      <span class="url-text">shlic://SHLNavigator.open?id=CDCLGFR0100MM01&amp;param={'PLAY'}</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLSharedPlatform.open?id=ACMCO29010010&param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D')">수퍼솔 이벤트1</button>
      <span class="url-text">shlic://SHLSharedPlatform.open?id=ACMCO29010010&amp;param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLSharedPlatform.open?id=ACMCO29010010&param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D')">수퍼솔 이벤트2</button>
      <span class="url-text">shlic://SHLSharedPlatform.open?id=ACMCO29010010&amp;param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D</span>
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
  padding: 10px;
}

.button-row {
  display: flex;
  align-items: center;
  margin: 10px 0;
  flex-wrap: wrap; /* Flex wrap to handle smaller screens */
}

.btn {
  margin-right: 15px;
  padding: 12px 24px; /* Slightly larger padding */
  font-size: 16px;
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f0f0f0;
  transition: background-color 0.2s ease;
  width: 100%; /* Full width on smaller screens */
  max-width: 280px; /* Max width for larger screens */
  box-sizing: border-box; /* Ensure proper padding behavior */
}

.btn:hover {
  background-color: #e0e0e0;
}

.url-text {
  font-size: 14px;
  color: #555;
  display: block;
  margin-top: 5px;
  word-break: break-all; /* Break long URLs if necessary */
}

@media (max-width: 600px) {
  .btn {
    font-size: 14px; /* Smaller font size for mobile */
    padding: 10px 18px; /* Slightly smaller padding for mobile */
  }

  .button-row {
    flex-direction: column; /* Stack buttons vertically on mobile */
    align-items: flex-start; /* Align text to the left */
  }

  .url-text {
    font-size: 12px; /* Smaller font size for mobile */
  }
}
</style>