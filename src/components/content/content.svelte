<script>
  import QRCode from "../qrcode/index.svelte";
  import CopyToClipboard from "svelte-copy-to-clipboard";
  import random from "random-string-generator";
  let walletaddress = "MLvQo3pj4W9VhalhP5HM";
  let icon_change = "fa fa-clone";
  const handleFailedCopy = () => {
    alert("failed to copy :(");
  };
  const generateAddress = (e) => {
    icon_change = "fa fa-clone";
    walletaddress = random(20);
  };
  const copyWalletAddress = () => {
    icon_change = "fa fa-check";
  };
</script>
<div class="p-4">
  <div class="row mt-4 p-4 mx-0" style="background-color: #f4f4f4">
    <div class="col-12 col-md-12">
      <h2 class="fw-bold mt-4">Deposit Cryptocurrency</h2>
    </div>
    <div class="col-md-6 col-lg-6 col-12 my-4">
      <label for="" class="control-label">Currency</label>
      <div class="col-lg-12 col-12">
        <div class="input-group">
          <label class="input-group-text" for="coinselect">
            <i class="fab fa-bitcoin fa-2x" style="color:orange"></i>
          </label>
          <select class="form-control" style="" id="coinselect" name="coinselect">
            <option value="0">BTC</option>
            <option value="1">ETH</option>
          </select>
        </div>
      </div>
      <div class="d-flex justify-content-between">
        <div>Minimum deposit <strong>-0.5BTC</strong></div>
        <div>Your fee <strong>-1%</strong></div>
      </div>
    </div>
    <div class="col-md-6 col-lg-6 col-12 my-4">
      <label for="" class="control-label">Network</label>
      <div
        class="col-lg-12 col-12 d-flex"
        style="justify-content: space-between; align-items:baseline"
      >
        <span class="fw-bold fs-3">ERC20</span>
        <span>Number of confirmation&emsp;<strong>-12 Blocks</strong></span>
      </div>
    </div>
    <div class="col-lg-6 col-12 my-4">
      <button
        type="button"
        class="btn btn-primary pt-3 pb-3 px-5 py-5 fw-bold"
        on:click={generateAddress}>GENERATE ADDRESS</button
      >
    </div>
    <div class="col-lg-6 col-12 my-4 d-flex">
      <div>
        <i class="fa fa-exclamation-circle" style="color:orange" />
      </div>
      <div class="mx-2">
        Ensure the network you choose to deposite matches the withdrawal
        network, or assets may be lost
      </div>
    </div>
    <div class="col-lg-4 col-12 my-4">
      <h3 style="color: #001c44;">Wallet Address</h3>
      <div class="mx-5 mt-5 my-6 col-8 card">
        <div
          class="align-items-center justify-content-center mx-auto pt-4 pb-4"
        >
          <QRCode codeValue={walletaddress} squareSize="200" />
          <div class="mt-4">
            <span>{walletaddress}</span>
            <CopyToClipboard
              text={walletaddress}
              on:copy={copyWalletAddress}
              on:fail={handleFailedCopy}
              let:copy
            >
              <button style="display:contents" on:click={copy}>
                <i class={icon_change} style="color: #0d6efd;" />
              </button>
            </CopyToClipboard>
          </div>
        </div>
      </div>
    </div>
    <div class="col-lg-8 col-12 mb-4 d-flex flex-column-reverse">
      <div class="d-flex mb-4">
        <div>
          <i class=" fa fa-exclamation" style="color: blue;" />
        </div>
        <div class="mx-2">
          Please choose only BTC to deposite to this address from your withdraw
          wallet
        </div>
      </div>
    </div>
  </div>
</div>
