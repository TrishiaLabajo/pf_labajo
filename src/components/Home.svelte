<script>
</script>


  <div class="home-container">
    <div class="text-container">
      <h2 class="title">BSCS STUDENT</h2>
      <p class="greeting">Hi, I'm <span class="accent">Trishia</span></p>
    </div>
    <img src="pictures\home.jpg" alt="Trishia Photo" title="Trishia Photo" class="profile-picture" />
  </div>



<style>

  .home-container {
    display: flex;
    justify-content: center; /* Center the content */
    align-items: center;
    height: 100vh;
    padding: 22rem 5rem;
    background-color: #c3b091; /* Dark background from AboutMe */
    color: #070707; /* Light text color from AboutMe */
    font-family: 'Calibri'; /* Add a clean font */
    width: 100%;
  }

  .profile-picture {
    width: 310px;
    height: auto;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Add a subtle shadow */
  }

  .text-container {
    text-align: left; /* Align text to the left */
    padding-right: 4rem; /* Increase padding for better spacing */
  }

  .title {
    font-size: 2.5rem; /* Make the title slightly larger */
    font-weight: bold;
    margin-bottom: 1rem;
    text-transform: uppercase; /* Capitalize the title */
  }

  .greeting {
    font-size: 2.5rem; /* Increase font size */
    font-weight: 600; /* Make it slightly bolder */
  }

  .accent {
    color: #2A3663; /* Add the accent color */
  }

  /* Responsive Styling */
  @media (max-width: 650px) {
    .home-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      height: 100vh;
      padding: 2rem; /* Reduce padding for mobile */
    }

    .profile-picture {
      width: 300px; /* Make the image smaller */
      height: auto;
      border-radius: 10px;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Add a subtle shadow */
      margin-bottom: 1rem;
    }

    .text-container {
      text-align: center; /* Align text to the left */
      padding-right: 0; /* Increase padding for better spacing */
      padding-bottom: 15px;
    }

    .title {
      font-size: 1.5rem; /* Adjust title size for mobile */
      font-weight: bold;
      margin-bottom: 1rem;
      text-transform: uppercase; /* Capitalize the title */
    }

    .greeting {
      font-size: 2rem; /* Adjust greeting size for mobile */
      font-weight: 600; /* Make it slightly bolder */
    }
  }
</style>