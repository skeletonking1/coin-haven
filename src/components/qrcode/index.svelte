<script>
  import QrCode from "svelte-qrcode";
  export let codeValue;
</script>

<div id="qrcode">
  <QrCode value={codeValue} />
</div>

<style>
</style>
