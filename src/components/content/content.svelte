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
        <select class="form-control selectpicker">
          <option value="fa fa-bitcoin"><svg aria-hidden="true" focusable="false" data-prefix="fab" data-icon="bitcoin" class="svg-inline--fa fa-bitcoin fa-w-16" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M504 256c0 136.967-111.033 248-248 248S8 392.967 8 256 119.033 8 256 8s248 111.033 248 248zm-141.651-35.33c4.937-32.999-20.191-50.739-54.55-62.573l11.146-44.702-27.213-6.781-10.851 43.524c-7.154-1.783-14.502-3.464-21.803-5.13l10.929-43.81-27.198-6.781-11.153 44.686c-5.922-1.349-11.735-2.682-17.377-4.084l.031-.14-37.53-9.37-7.239 29.062s20.191 4.627 19.765 4.913c11.022 2.751 13.014 10.044 12.68 15.825l-12.696 50.925c.76.194 1.744.473 2.829.907-.907-.225-1.876-.473-2.876-.713l-17.796 71.338c-1.349 3.348-4.767 8.37-12.471 6.464.271.395-19.78-4.937-19.78-4.937l-13.51 31.147 35.414 8.827c6.588 1.651 13.045 3.379 19.4 5.006l-11.262 45.213 27.182 6.781 11.153-44.733a1038.209 1038.209 0 0 0 21.687 5.627l-11.115 44.523 27.213 6.781 11.262-45.128c46.404 8.781 81.299 5.239 95.986-36.727 11.836-33.79-.589-53.281-25.004-65.991 17.78-4.098 31.174-15.792 34.747-39.949zm-62.177 87.179c-8.41 33.79-65.308 15.523-83.755 10.943l14.944-59.899c18.446 4.603 77.6 13.717 68.811 48.956zm8.417-87.667c-7.673 30.736-55.031 15.12-70.393 11.292l13.548-54.327c15.363 3.828 64.836 10.973 56.845 43.035z"></path></svg> BTC</option>
          <option value="1">
            <i
              class="fa fa-bitcoin"
              style="color:white; background:orange"
            />BTC
          </option>
        </select>
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
