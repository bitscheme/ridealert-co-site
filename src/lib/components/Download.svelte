<script>
  import { Smartphone } from 'lucide-svelte';
</script>

<section id="download" class="section bg-gradient">
  <div class="container">
    <div class="call-to-action">
      <div class="box-icon">
        <Smartphone size={32} color="var(--primary)" />
      </div>
      <h2>Download</h2>
      <p class="tagline">Available for iOS, macOS and Android platforms.</p>
      <div class="buttons">
        <a href="https://play.google.com/store/apps/details?id=com.bitscheme.ridealert" class="store-link">
          <img src="/images/GetItOnGooglePlay_Badge_Web_color_English.png" alt="Get it on Google Play">
        </a>
        <a href="https://itunes.apple.com/us/app/ride-alert-social-cycling/id1211768218" class="store-link">
          <img src="/images/Download_on_the_App_Store_Badge_US-UK_RGB_blk_092917.svg" alt="Download on the App Store">
        </a>
        <a href="https://apps.apple.com/us/app/ride-alert-social-cycling/id1211768218" class="store-link">
          <img src="/images/Download_on_the_Mac_App_Store_Badge_US-UK_RGB_blk_092917.svg" alt="Download on the Mac App Store">
        </a>
      </div>
    </div>
  </div>
</section>

<style>
  .call-to-action {
    text-align: center;
    color: white;
  }
  
  .box-icon {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    width: 70px;
    height: 70px;
    background: white;
    border-radius: 8px;
    margin-bottom: 2rem;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    font-size: 2rem;
  }
  
  h2 {
    color: white;
    margin-bottom: 1rem;
    font-size: 2.5rem;
  }
  
  .tagline {
    font-size: 1.1rem;
    color: rgba(255,255,255,0.9);
    margin-bottom: 2.5rem;
  }
  
  .buttons {
    display: flex;
    justify-content: center;
    gap: 1.5rem;
    flex-wrap: wrap;
    margin-top: 1rem;
  }
  
  .store-link img {
    height: 48px;
    width: auto;
    transition: transform 0.2s;
  }

  .store-link:hover img {
    transform: scale(1.05);
  }
</style>
