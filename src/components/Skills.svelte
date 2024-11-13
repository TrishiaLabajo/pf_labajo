<script>
  const skills = [
    {
      name: "Svelte",
      description: "Build website using svelte."
    },
    {
      name: "HTML",
      description: "Create Website skeleton using HTML as markup language"
    },
    {
      name: "CSS",
      description: "Add designs and basic animation to my websites"
    }
    // Add more skills here...
  ];
</script>

<section class="skills" id="skills">
  <div class="skills-container">
    <h3>Skills</h3>
    <div class="skills-grid">
      {#each skills as skill}
          <div class="skill-text">
            <h4>{skill.name}</h4>
            <div class="skill-description">
              <p style="overflow: hidden;">{skill.description}</p>
            </div>
          </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .skills {
    padding: 40px;
    background-color: #c3b091; /* Dark background from AboutMe */
    color: black; /* Light text color from AboutMe */
    text-align: center;
  }

  .skills-container {
    max-width: 900px; /* Adjust as needed */
    margin: 0 auto; /* Center the container */
    font-family: 'Calibri';
  }
  .skills-container h3{
      font-size: 4rem;
      padding-bottom: 50px;
  }
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); /* Responsive grid */
    gap: 30px;
  }

  .skill-text {
    background-color: #af855c; /* Dark background for the text container */
    color: #fff; /* White text color */
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center; /* Center text horizontally */
    justify-content: center; /* Center text vertically */
    border-radius: 10px; /* Add border-radius for rounded corners */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add subtle shadow */
  }

  /* Responsive Styling */
  @media (max-width: 650px) {
    .skills-grid {
      grid-template-columns: 1fr; /* One column for mobile */
      gap: 20px; /* Adjust gap as needed */
    }

    .skill-text {
      width: 100%;
    }
  }
</style>