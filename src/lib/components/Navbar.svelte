<script>
  let isMenuOpen = false;

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }
</script>

<nav class="navbar">
  <div class="container">
    <a href="/" class="brand">
      <img src="/images/logo-transparent.png" alt="Ride Alert" width="75" height="75">
    </a>
    <button class="toggle" on:click={toggleMenu} aria-label="Toggle navigation">
      ☰
    </button>
    <div class="menu {isMenuOpen ? 'open' : ''}">
      <a href="#home" on:click={() => isMenuOpen = false}>HOME</a>
      <a href="#features" on:click={() => isMenuOpen = false}>FEATURES</a>
      <a href="#gallery" on:click={() => isMenuOpen = false}>GALLERY</a>
      <a href="#contact" on:click={() => isMenuOpen = false}>CONTACT</a>
      <a href="#download" class="btn" on:click={() => isMenuOpen = false}>Download</a>
    </div>
  </div>
</nav>

<style>
  .navbar {
    position: sticky;
    top: 0;
    z-index: 1000;
    background: var(--primary-gradient);
    padding: 0.5rem 0;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }
  
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: relative;
  }
  
  .brand img {
    height: 60px;
    width: auto;
  }
  
  .toggle {
    display: none;
    background: none;
    border: none;
    font-size: 1.5rem;
    color: white;
    cursor: pointer;
  }
  
  .menu {
    display: flex;
    align-items: center;
    gap: 1.5rem;
  }
  
  .menu a {
    color: white;
    font-size: 0.9rem;
    font-weight: 500;
    text-transform: uppercase;
    opacity: 0.9;
  }
  
  .menu a:hover {
    opacity: 1;
    color: white;
  }
  
  .menu .btn {
    color: var(--primary);
    background: white;
    margin-left: 1rem;
  }
  
  .menu .btn:hover {
    color: var(--secondary);
  }

  @media (max-width: 768px) {
    .toggle {
      display: block;
    }
    
    .menu {
      display: none;
      position: absolute;
      top: 100%;
      left: 0;
      right: 0;
      background: var(--primary);
      flex-direction: column;
      padding: 1rem;
      text-align: center;
      box-shadow: 0 10px 20px rgba(0,0,0,0.1);
    }
    
    .menu.open {
      display: flex;
    }
    
    .menu .btn {
      margin: 0;
    }
  }
</style>
