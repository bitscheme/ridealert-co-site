<footer class="footer">
  <p>
    <small>COPYRIGHT © {new Date().getFullYear()} BITSCHEME, LLC. ALL RIGHTS RESERVED.</small>
  </p>
  <div class="links">
    <a href="/terms">TERMS</a>
    <a href="/privacy">PRIVACY</a>
  </div>
</footer>

<style>
  .footer {
    text-align: center;
    padding: 2rem 0;
    font-size: 0.85rem;
    color: var(--text-muted);
    border-top: 1px solid rgba(0,0,0,0.05);
  }
  
  .links {
    margin-top: 0.5rem;
  }
  
  .links a {
    margin: 0 0.5rem;
    color: var(--text-muted);
  }
  
  .links a:hover {
    color: var(--primary);
  }
  
  @media (prefers-color-scheme: dark) {
    .footer {
      border-top-color: rgba(255,255,255,0.05);
    }
  }
</style>
