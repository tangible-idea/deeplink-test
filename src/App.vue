<template>
  <div class="container">
    <h1 class="title">Deeplink test</h1>

    <div class="button-row">
      <button class="btn" @click="navigateTo('shlic://SHLNavigator.open?id=CDCLGFR0100MM01&amp;param={\'PLAY\'}')">운세 (push)</button>
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

    <div>
        <br><br><br><br><br>
    </div>
    
    <!-- EditText1 for screen name -->
    <div class="input-row">
      <label for="screenName">화면명</label>
      <input list="screenIds" id="screenName" v-model="screenName" class="input-text" placeholder="Enter screen name (?id=CDCBCCO0700NP02)" />
      <!-- Datalist for autocomplete suggestions -->
      <datalist id="screenIds">
        <option v-for="id in screenIdList" :key="id" :value="id">{{ id }}</option>
      </datalist>
    </div>

    <!-- EditText2 for parameter -->
    <div class="input-row">
      <label for="param">파라미터</label>
      <input type="text" id="param" v-model="param" class="input-text" placeholder="Enter parameter (optional, &amp;param=something)" />
    </div>

    <!-- Generated Deeplink -->
    <div class="button-row">
      <span class="url-text">{{ generatedDeeplink }}</span>
    </div>

    <!-- Button to navigate to the generated Deeplink -->
    <div class="button-row">
      <button class="btn" @click="navigateTo(generatedDeeplink)">이동하기</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      screenName: '', // Variable for the screen name (EditText1)
      param: '',      // Variable for the parameter (EditText2)
      // List of screen IDs for autocomplete
      screenIdList: [
        "CDCBCCO0500NP03",
        "CDCBCCO0500NP17",
        "CDCBCCO0500NP18",
        "CDCBCCO0500NP19",
        "CDCBCCO0500NP20",
        "CDCBCCO0500NP25",
        "CDCBCCO0500NP26",
        "CDCBCCO0500NP29",
        "CDCBCCO0700NM01",
        "CDCBCCO0700NM02",
        "CDCBCCO0700NP02",
        "CDCBCCO0700NP12",
        "CDCBCLI0100NM01",
        "CDCBCLI0100NP01",
        "CDCBCLI0100NP02",
        "CDCBCLI0100NP03",
        "CDCBCLI0100NP04",
        "CDCBCLI0100NP05",
        "CDCBCLI0100NP06",
        "CDCBCLI0100NP07",
        "CDCBCLI0100NP08",
        "CDCBCLI0100NP13",
        "CDCBCLI0100NP16",
        "CDCBCLI0100NP17",
        "CDCBCLI0100NP18",
        "CDCBCLI0100NP19",
        "CDCBCLI0100NP20",
        "CDCBCLI0100NP21",
        "CDCBCLI0200NP03"
      ]
    };
  },
  computed: {
    // Computed property to generate the deeplink based on screenName and param
    generatedDeeplink() {
      if (this.screenName) {
        // If param is provided, include it in the URL; otherwise, omit it
        return this.param
          ? `shlic://SHLNavigator.open?id=${this.screenName}&param=${this.param}`
          : `shlic://SHLNavigator.open?id=${this.screenName}`;
      } else {
        return 'Enter a screen name';
      }
    }
  },
  methods: {
    navigateTo(url) {
      // Only navigate if the URL is valid (i.e., not the placeholder text)
      if (url.startsWith('shlic://')) {
        window.location.href = url;
      } else {
        alert('유효한 화면명을 입력하세요.');
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

.input-row {
  display: flex;
  flex-direction: column;
  margin-bottom: 15px;
  width: 100%;
  max-width: 500px;
}

label {
  font-size: 14px;
  margin-bottom: 5px;
  color: #555;
}

.input-text {
  padding: 10px;
  font-size: 16px;
  width: 100%;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
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
  max-width: 500px;
  box-sizing: border-box;
}

.btn:hover {
  background-color: #e0e0e0;
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