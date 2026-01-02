<section id="features" class="section light-bg">
  <div class="container">
    <div class="section-title">
      <small>HIGHLIGHTS</small>
      <h3>Ride With Local Cyclists</h3>
    </div>

    <div class="grid">
      <!-- Feature 1 -->
      <div class="card feature">
        <div class="icon">User</div>
        <h4>Connect</h4>
        <p>Ride Alert is the app to connect you with the local cycling scene. Signup with your email address, connect your Strava account and start riding with other cyclists.</p>
      </div>
      <!-- Feature 2 -->
      <div class="card feature">
        <div class="icon">Map</div>
        <h4>Post Your Ride</h4>
        <p>Let other cyclists in your city know about your upcoming ride. Enter details like start date, time, location, and distance.</p>
      </div>
      <!-- Feature 3 -->
      <div class="card feature">
        <div class="icon">Check</div>
        <h4>Join Up</h4>
        <p>See a ride you like? Let everyone know by indicating if you are in, out or undecided.</p>
      </div>
      <!-- Feature 4 -->
      <div class="card feature">
        <div class="icon">Chat</div>
        <h4>Chat</h4>
        <p>Tired of using group text to set the ride details? Each ride provides real time chat.</p>
      </div>
      <!-- Feature 5 -->
      <div class="card feature">
        <div class="icon">Bell</div>
        <h4>Alerts</h4>
        <p>Receive push notifications for public and private rides, join ups and new chat messages.</p>
      </div>
      <!-- Feature 6 -->
      <div class="card feature">
        <div class="icon">Lock</div>
        <h4>Private Rides</h4>
        <p>Want to invite your buddies on a private ride? Create and send "invitation only" rides that are hidden from public view.</p>
      </div>
    </div>
  </div>
</section>

<style>
  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .card {
    background: white;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 4px 6px rgba(0,0,0,0.05);
    transition: transform 0.3s ease;
    text-align: left;
    height: 100%;
  }
  
  .card:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 20px rgba(0,0,0,0.1);
  }
  
  .icon {
    font-size: 1.5rem;
    color: var(--primary);
    margin-bottom: 1rem;
    width: 50px;
    height: 50px;
    background: rgba(252, 76, 2, 0.1);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  h4 {
    margin-bottom: 1rem;
    font-size: 1.25rem;
  }
  
  p {
    color: var(--text-muted);
    font-size: 0.95rem;
    line-height: 1.6;
    margin: 0;
  }
  
  /* Dark mode overrides for card */
  @media (prefers-color-scheme: dark) {
    .card {
      background: #333;
    }
    .icon {
      background: rgba(255,255,255,0.1);
    }
  }
</style>
