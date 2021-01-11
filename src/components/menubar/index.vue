<template>
  <div class="menubar">
    <ul class="menu">
      <li>
        <a>
          <span>首页</span>
        </a>
      </li>
      <li>
        <a>
          <span>今日热门</span>
        </a>
      </li>
      <li>
        <a>
          <span>月度排行</span>
        </a>
      </li>
      <li>
        <a>
          <span>时尚热度</span>
        </a>
      </li>

    </ul>
    <div class="marker"></div>
  </div>
</template>

<script>
export default {
  name: "menubar",
  props: {}
};
</script>

<style lang="scss">
.menubar {
  width: 100%;
  height: 30px;
  margin-top: 10px;

  .marker {
    width: 31px;
    height: 4px;
    background: rgba(255, 127, 0, 1);
  }

  ul {
    width: 100%;
    height: 30px;
    position: fixed;
    left: 140px;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;

    li {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-right: 29px;
      cursor: pointer;

      a {
        span {
          height: 15px;
          font-size: 16px;
          font-family: MicrosoftYaHei;
          font-weight: 400;
          color: rgba(255, 255, 255, 1);
        }
      }
    }
  }
}
</style>
