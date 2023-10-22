<script>
  let expanded = false;
</script>

<div id="nav-menu" class:expanded>
  <div id="nav-overlay">&nbsp;</div>
  <navigation>
    <button on:blur={() => expanded = false} on:click={() => expanded =! expanded}>
      <div class="line">&nbsp;</div>
      <div class="menu-container">
        <ul>
          <li><a href="#top">Top</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#services">Services</a></li>
          <li><a href="#contact">Contact</a></li>
        </ul>
      </div>
      <div class="line">&nbsp;</div>
    </button>
  </navigation>
</div>

<style>

  #nav-overlay {
    display: none;
    background: rgba(0, 0, 0, 0.5);
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
  }

  ul a {
    text-decoration: none;
    color: white;
    font-size: 1.5rem;
    font-weight: 600;
    display: block;
    padding: 10px 0;
    transition: all 0.1s ease-in-out;
  }

  @media screen and (min-width: 1024px) {
    navigation {
      position: absolute;
      top: 16px;
      right: 16px;
      z-index: 100;
    }

    button {
      outline: none;
      border: none;
      background: none;
      display: flex;
      flex-direction: column;
      align-items: stretch;
      gap: 4px;
    }

    .menu-container {
      overflow: hidden;
    }

    ul {
      list-style-type: none;
      padding: 0;
      text-align: right;
      margin-top: -150%;
      margin-bottom: 0;
      padding-left: 3rem;
      transition: all 0.6s cubic-bezier(0.33, 1, 0.68, 1);
    }

    navigation:hover ul {
      margin-top: 0;
    }


    ul a:hover {
      color: #7e7e7e;
    }

    ul a::after {
      display: none;
      content: '';
    }

    .line {
      border-radius: 2px;
      height: 4px;
      background: white;
      display: block;
    }
  }

  @media screen and (max-width: 1024px) {

    #nav-menu.expanded #nav-overlay {
      display: block;
    }

    @keyframes fade-in {
      from {
        opacity: 0;
      }
      to {
        opacity: 1;
      }
    }

    #nav-menu.expanded #nav-overlay {
      animation-name: fade-in;
      animation-duration: 0.3s;
      animation-timing-function: ease-in-out;
    }

    navigation {
      position: absolute;
      top: 16px;
      right: 16px;
    }

    navigation button {
      border: none;
      background: none;
      display: flex;
      flex-direction: column;
      align-items: stretch;
      gap: 4px;
    }

    .line {
      border-radius: 1px;
      height: 2px;
      background: white;
      display: block;
      min-width: 24px;
    }

    #nav-menu:not(.expanded) navigation .menu-container {
      display: none;
    }

    .menu-container {
      overflow: hidden;
    }

    @keyframes slide-in {
      from {
        margin-top: -150%;
      }
      to {
        margin-top: 0;
      }
    }

    #nav-menu.expanded navigation ul {
      list-style-type: none;
      padding: 0;
      text-align: right;
      margin-bottom: 0;
      padding-left: 3rem;

      animation-name: slide-in;
      animation-timing-function: cubic-bezier(0.165, 0.84, 0.44, 1);
      animation-duration: 0.6s;
    }

    navigation:hover ul {
      margin-top: 0;
    }
  }
</style>