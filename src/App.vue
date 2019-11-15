<template>
  <div id="app">
    <div class="wrapper">
      <custom-button
              :size="size"
              :variant="variant"
              :disabled="disabled"
      ></custom-button>
      <div class="settings">
        <div class="flex-between">
          <input type="text" v-model="size" placeholder="Enter size">
          <span class="info" :title="sizeInfo">ⓘ</span>
        </div>
        <div class="flex-between">
          <input type="text" v-model="variant" placeholder="Enter variant">
          <span class="info" :title="variantInfo">ⓘ</span>
        </div>
        <label>
          <input type="checkbox" v-model="disabled">
          Disabled Button
        </label>
      </div>
    </div>
  </div>
</template>

<script>
import customButton from "./components/customButton";

export default {
  name: 'app',
  data() {
    return {
      size: "",
      variant: "",
      disabled: false,
      sizeInfo: "Enter: lg or sm",
      variantInfo: "Enter: primary, success, danger, warning or text"
    }
  },
  components: {
    customButton
  }
}
</script>

<style lang="scss">
  *{
    margin: 0;
    padding: 0;
    font-family: sans-serif;
  }
  .wrapper {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;

    .settings {
      margin-top: 50px;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-gap: 30px;

      .flex-between {
        display: flex;
        align-items: center;
        justify-content: space-between;

        .info {
          margin-left: 10px;
          cursor: pointer;
          font-weight: bold;
          color: #1867c0;
        }
      }
    }
  }
</style>
