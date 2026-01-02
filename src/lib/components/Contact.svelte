<section id="contact" class="light-bg">
  <div class="container">
    <div class="content">
      <div class="location">
        <p>Made with ❤️ in <a href="https://en.wikipedia.org/wiki/Tulsa,_Oklahoma">Tulsa, Oklahoma</a></p>
        <p><a href="mailto:info@ridealert.co">info@ridealert.co</a></p>
      </div>
      <div class="socials">
        <a href="https://www.facebook.com/RideAlertApp">Facebook</a>
        <a href="https://www.twitter.com/ridealert_app">Twitter</a>
        <a href="https://www.instagram.com/ridealertapp">Instagram</a>
      </div>
    </div>
  </div>
</section>

<style>
  #contact {
    padding: 3rem 0;
  }
  
  .content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
    gap: 2rem;
  }
  
  .location p {
    margin: 0.25rem 0;
    color: var(--text-muted);
  }
  
  .socials {
    display: flex;
    gap: 1rem;
  }
  
  .socials a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 40px;
    height: 40px;
    background: white;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    border-radius: 4px;
    font-size: 0; /* Hide text, assuming icons will be added or we leave text */
    color: var(--primary);
  }
  
  .socials a:hover {
    color: var(--link-hover);
    transform: translateY(-2px);
  }
  
  /* Temporary: if we don't have icons, show text */
  .socials a {
    font-size: 0.8rem;
    width: auto;
    padding: 0 1rem;
  }
  
  @media (prefers-color-scheme: dark) {
    .socials a {
      background: #333;
      color: #fff;
    }
  }
</style>
