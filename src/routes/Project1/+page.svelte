<script>
  import { goto } from '$app/navigation';
</script>

<header class="header">
  <div class="container">
    <img src="pictures/trishlogo.png" alt="Trish Logo" title="Trish Logo" />
    <button class="return-button" on:click={() => goto('/#Projects')}>Return</button>
  </div>
</header>

<div class="project-details">
  <h2 class="project-title">Sari Stock - POS</h2>

  <div class="project-grid">
    <div class="project-item">
      <img src="Project1_Files/SariStock.png" alt="Sari Stock Logo" title="Sari Stock Logo" class="project-logo" />
      <div class="project-description">
        <p>Sari-Sari stock is a basic POS system that could comply to a basic needs of a small scale Sari-Sari store.</p>
      </div>
    </div>
    <div class="project-item">
      <div class="project-header">
        <h2>Login Page</h2>
      </div>
      <img src="Project1_Files/Login.png" alt="Login Page" title="Login Page" class="project-image" />
      <div class="project-description">
        <p>The Login page lets you access the system features</p>
      </div>
    </div>
    <div class="project-item">
      <div class="project-header">
        <h2>Home Page</h2>
      </div>
      <img src="Project1_Files/Home.png" alt="Home Page" title="Home Page" class="project-image" />
      <div class="project-description">
        <p>The home page of the system where all features of the system is mostly located</p>
      </div>
    </div>
    <div class="project-item">
      <div class="project-header">
        <h2>Manage Product Page</h2>
      </div>
      <img src="Project1_Files/Products.png" alt="Manage Product Page" title="Manage Product Page" class="project-image" />
      <div class="project-description">
        <p>The product management page where you can monitor and control the amounts and prices of products.</p>
      </div>
    </div>
    <div class="project-item">
      <div class="project-header">
        <h2>Transcation Page</h2>
      </div>
      <img src="Project1_Files/Cart.png" alt="Transaction Page" title="Transaction Page" class="project-image" />
      <div class="project-description">
        <p>This where transaction happens, such as deducting of product in the database and showing total amount of products bought.</p>
      </div>
    </div>
    <div class="project-item">
      <div class="project-header">
        <h2>Sales Record Page</h2>
      </div>
      <img src="Project1_Files/Sales.png" alt="Sales Record Page" title="Sales Record Page" class="project-image" />
      <div class="project-description">
        <p>This is where you can monitor the procucts sold with search filtering feature</p>
      </div>
    </div>
    <div class="project-item">
      <div class="project-header">
        <h2>Database</h2>
      </div>
      <img src="Project1_Files/Database.png" alt="Database Design" title="Databse Design" class="project-image" />
      <div class="project-description">
        <p>And finally, this is the database of Sari-Stock that stores important data of a Sari-Sari stores products, sales, and transactions.</p>
      </div>
    </div>
  </div>
</div>

<style>
  .project-details {
    padding: 2rem;
    background-color: #c3b091;
    color: black;
    font-family: 'Calibri';
    text-align: center;
    padding-top: 60px; /* Add padding to account for the fixed header */
  }

  .project-title {
    font-size: 3rem;
    margin-bottom: 1rem;
    font-weight: bold;
    text-transform: uppercase;
  }

  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
    margin-bottom: 2rem;
  }

  .project-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #af855c;
    padding: 1rem;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }

  .project-logo {
    width: 250px;
    height: auto;
  }

  .project-image {
    width: 100%;
    max-width: 250px;
    height: auto;
    margin-bottom: 1rem;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }

  .project-description {
    margin-top: 1rem;
    line-height: 1.6;
    text-align: center;
  }

  .project-description p {
    margin-bottom: 1rem;
  }

  .project-header {
    display: flex;
    justify-content: flex-start; /* Align the header to the right */
    width: 100%;
    margin-bottom: 1rem;
  }

  .project-header h2 {
    font-size: 1.5rem;
    font-weight: bold;
    color: #2A3663;
  }

  /* Header Styles */
  .header {
    background-color: #c3b091; /* Dark background */
    color: #2A3663; /* Light text color */
    padding: 0.5rem 0;
    position: fixed; /* Fix the header to the top */
    top: 0;
    left: 0;
    width: 100%;
    z-index: 10; /* Ensure header stays on top */
  }

  .container {
    display: flex;
    justify-content: space-between; /* Space between logo and menu-toggle */
    align-items: center;
    max-width: 520px;
    margin: 0 auto;
  }

  img {
    height: 40px;
  }

  .return-button {
    background-color: #2A3663; /* Accent color for the button */
    color: #ECDFCC; /* Light text color */
    padding: 0.6rem 2rem;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    margin-left: 1rem; /* Add space between button and logo */
  }


  /* Media Query for Mobile Devices (650px or less) */
  @media (max-width: 650px) {
    .project-grid {
      grid-template-columns: 1fr; /* Single column for mobile */
    }

    .project-image {
      width: 250px; /* Adjust image width for mobile */
    }

    .container{
      max-width: 300px;
    }

    .project-header {
      justify-content: center; /* Center the header on mobile */
    }
  }
</style>