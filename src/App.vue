<template>
  <div class="container">
    <h1 class="title">Deeplink test</h1>
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
      <input type="text" v-model="customUrl" class="input-text" placeholder="shlic://"/>
      <button class="btn" @click="navigateTo(customUrl)">위 입력한 딥링크로 이동</button>
      <span class="url-text">{{ customUrl }}</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      customUrl: '' // The text input for the custom URL
    };
  },
  methods: {
    navigateTo(url) {
      if (url) {
        window.location.href = url;
      } else {
        alert('URL을 입력하세요.');
      }
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
  width: 100%;
  box-sizing: border-box;
}

.title {
  font-size: 24px;
  font-weight: bold;
  margin-bottom: 20px;
  text-align: center;
  color: #333;
}

.button-row {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 10px 0;
  width: 100%;
}

.btn {
  padding: 12px 24px;
  font-size: 16px;
  cursor: pointer;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f0f0f0;
  transition: background-color 0.2s ease;
  width: 100%;
  max-width: 100%;
  box-sizing: border-box;
}

.btn:hover {
  background-color: #e0e0e0;
}

.input-text {
  padding: 10px;
  font-size: 16px;
  width: 100%;
  max-width: 100%;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
  margin-bottom: 10px;
}

.url-text {
  font-size: 14px;
  color: #555;
  display: block;
  margin-top: 5px;
  word-break: break-all;
  width: 100%;
  text-align: center;
}

/* Media queries for larger screens */
@media (min-width: 768px) {
  .btn {
    width: 500px;
  }

  .input-text {
    width: 500px;
  }
}

@media (max-width: 600px) {
  .btn {
    font-size: 14px;
    padding: 10px 18px;
  }

  .input-text {
    font-size: 14px;
    padding: 8px;
  }

  .url-text {
    font-size: 12px;
  }
}
</style>