<template>
  <div class="container">
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLNavigator.open?id=CDCLGFR0100MM01&amp;param={\'PLAY\'}')">운세</button>
      <span class="url-text">shlic://SHLNavigator.open?id=CDCLGFR0100MM01&amp;param={'PLAY'}</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLSharedPlatform.open?id=ACMCO29010010&amp;param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D')">수퍼솔 이벤트1</button>
      <span class="url-text">shlic://SHLSharedPlatform.open?id=ACMCO29010010&amp;param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLSharedPlatform.open?id=ACMCO29010010&amp;param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D')">수퍼솔 이벤트2</button>
      <span class="url-text">shlic://SHLSharedPlatform.open?id=ACMCO29010010&amp;param=%7B%22pId%22%3A%22ABFSF01020010P03%22%7D</span>
    </div>
    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLNavigator.open?id=CDCBCCO0200MP01')">이용기기 등록 테스트</button>
      <span class="url-text">CDCBCCO0200MP01</span>
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
  width: 100%; /* Ensure the container is full width */
  box-sizing: border-box;
}

.button-row {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 10px 0;
  width: 100%; /* Ensure the button-row takes full width */
}

.btn {
  padding: 12px 24px;
  font-size: 16px;
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f0f0f0;
  transition: background-color 0.2s ease;
  width: 100%; /* Default for mobile */
  max-width: 100%; /* Ensure no overflow beyond the container */
  box-sizing: border-box; /* Ensures proper padding behavior */
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
  width: 100%; /* Ensure text takes full width */
  text-align: center; /* Center the text for a cleaner look */
}

/* Media queries for larger screens (e.g., PC) */
@media (min-width: 768px) {
  .btn {
    width: 500px; /* On larger screens, limit the button width to 500px */
  }
}

@media (max-width: 600px) {
  .btn {
    font-size: 14px; /* Smaller font size for mobile */
    padding: 10px 18px; /* Slightly smaller padding for mobile */
  }

  .url-text {
    font-size: 12px; /* Smaller font size for mobile */
  }
}
</style>