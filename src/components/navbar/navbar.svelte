<script>
  // import userAvatar from './100.jpg';
</script>

<nav
  class="navbar sticky-top flex-md-nowrap p-3 shadow d-flex justify-content-between"
  style="background-color: white; z-index: 99999"
>
  <a
    class="col-md-3 col-lg-2 mr-0 px-3 text-decoration-none"
    style="color: #6c757d;"
    href="/"
  >
    <i class="fa fa-angle-left" />&emsp;Back to Fiat and Spot
  </a>
  <div class="d-flex align-items-center">
    <button type="button" class="btn position-relative">
      <i class="fa fa-bell fa-2x" />
      <span
        class="position-absolute start-70 translate-middle p-1 bg-danger border border-light rounded-circle"
      >
        <span class="visually-hidden">New alert</span>
      </span>
    </button>
      <!-- <image src={userAvatar} width="35"/> -->
    <button
      type="button"
      id="dropdownCurrency"
      class="btn btn-sm border-0 btn-outline-secondary dropdown-toggle"
    >
      English/USD
    </button>
    <ul class="navbar-nav">
      <li class="nav-item text-nowrap" />
    </ul>
    <ul class="navbar-nav px-3">
      <li class="nav-item text-nowrap">
        <a class="nav-link" href="/" style="color:#6c757d">Download</a>
      </li>
    </ul>
  </div>
</nav>
