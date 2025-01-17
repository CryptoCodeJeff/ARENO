<script lang="ts">
  let ca = 'F9YaWZB2pvhf412XYX6Lq5eYF7dhV1ePWtjJesKgpump'
  let show = false

  const copy = () => {
    navigator.clipboard.writeText(ca)
    show = true

    setTimeout(() => (show = false), 1000)
  }
</script>

<style lang="scss">
  @use 'src/sass/mixins.scss' as *;

  button {
    position: relative;
    transition: 0.3s ease !important;
    text-align: center;
    width: 100%;
    font-size: 24px;
    background-image: url('/assets/banner.png');
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    height: 300px;

    @include notDesktop {
      font-size: 14px;
      height: 200px;
    }

    &:hover {
      box-shadow: 0px 0px 0px 0px rgba(0, 0, 0, 0.3);
      transform: scale(0.9);
    }
  }
</style>

<button class="link" on:click={copy}> {show ? 'Copied to clipboard!' : ca} </button>
