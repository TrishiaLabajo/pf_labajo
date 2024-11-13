<script>
  import { goto } from '$app/navigation';
</script>

<div class="projects-container" id="Projects">
  <h2 class="projects-header">Projects</h2>
  <div class="project-grid">
    <div class="project">
      <img src="Project1_Files/SariStock.png" alt="Sari Stock Logo" title="Sari Stock Logo" class="project-image" />
      <div class="project-content">
        <h3>Sari Stock - POS</h3>
        <p>A simple POS application for a small scale Sari-Sari Store</p>
        <button class="see-more-button" on:click={() => goto('/Project1')}>See More <span class="arrow">→</span></button>
      </div>
    </div>
    </div>
</div>

<style>
  .projects-container {
    padding: 2rem;
    background-color: #c3b091; /* Dark background color */
    color: black; /* Light text color */
    font-family: 'Calibri'; /* Match the font from other components */
    display: flex;
    flex-direction: column;
    align-items: center; /* Center the content horizontally */
  }

  .projects-header {
    font-size: 4rem;
    margin-bottom: 2rem;
    text-transform: uppercase; /* Capitalize the title */
    font-weight: bold;
  }

  .project-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive grid layout */
    gap: 2rem;
  }

  .project {
    display: flex;
    flex-direction: column; /* Stack image and content vertically */
    align-items: center;
    background-color: #af855c; /* Lighter background for project */
    padding: 1rem;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add subtle shadow */
  }

  .project-image {
    width: 100%;
    max-width: 250px; /* Adjust image width as needed */
    height: auto;
    margin-bottom: 1rem; /* Add space below the image */
    border-radius: 8px;
  }

  .project-content {
    text-align: center; /* Center the description */
  }

  .project-content h3 {
    color: #2A3663; /* Accent color for project titles */
    margin-bottom: 1rem;
    font-size: 1.5rem;
  }

  .project-content p {
    font-size: 1rem;
    line-height: 1.5;
    padding-bottom: 20px;
  }

  .see-more-button {
    background-color: #2A3663; /* Accent color for the button */
    color: #ECDFCC; /* Light text color */
    padding: 0.8rem 2rem;
    border: none;
    border-radius: 8px;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s ease-in-out; /* Add a transition for hover effect */
  }

  .see-more-button:hover {
    background-color: #008080; /* Change background color on hover */
  }

  .arrow {
    font-size: 1.2rem;
  }

  /* Media Query for Mobile Devices (650px or less) */
  @media (max-width: 650px) {
    .project-grid {
      grid-template-columns: 1fr; /* Single column for mobile */
    }

    .project-image {
      width: 100%;
    }

    .projects-header {
      font-size: 3.5rem;
    }
  }
</style>