<script>
  let showSkills = true;
  let showEducation = false;

  const toggleSection = () => {
    showSkills = !showSkills;
    showEducation = !showEducation;
  };

  const skills = [
    {
      name: "Web Development",
      description: "Create Website with the use of frameworks"
    }
  ];

  const education = [
    {
      year: "2024",
      level: "College Undergrad - CvSU",
      description: "Currently pursuing my dram on Bachelor of Science in Computer Sciece"
    },
    {
      year: "2021",
      level: "SEAT",
      description: "Completed Senior High School with TVL track."
    },
    {
      year: "2013",
      level: " Queens Row Elementary",
      description: "Finished Elementary School with few achievements"
    }
  ];
</script>

<div class="main-container"> <section class="about-me" id="about">
  <div class="content-container">
    <div class="heading-container">
      <h2 class="about-me-heading">About Me</h2>
    </div>
    <div class="profile">
      <div class="info-container">
        <p>I am Trishia Mae A. Labajo an aspiring student pursuing to be a proffesional Software Engineer.</p>
        <div class="options">
          <button on:click={toggleSection} class={showSkills ? 'active' : ''}>Skills</button>
          <button on:click={toggleSection} class={showEducation ? 'active' : ''}>Education</button>
        </div>
        <div class="section-container">
          {#if showSkills}
            <div class="skills-info">
              <h3>Skills</h3>
              {#each skills as skill}
                <div class="skill-item">
                  <h4>{skill.name}</h4>
                  <p>{skill.description}</p>
                </div>
              {/each}
            </div>
          {/if}
          {#if showEducation}
            <div class="education-info">
              <h3>Education</h3>
              {#each education as edu}
                <div class="skill-item">
                  <h4>{edu.year} - {edu.level}</h4>
                  <p>{edu.description}</p>
                </div>
              {/each}
            </div>
          {/if}
        </div>
      </div>
      <div class="image-container">
        <img src="pictures\about.jpg" alt="Jymce Bertillo Photo" title="Jymce Bertillo Photo" />
      </div>
    </div>
  </div>
</section>
</div>

<style>
.about-me {
  background-color: #c3b091;
  color: black;
  text-align: center;
}

.content-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 1000px; /* Adjust max-width as needed */
  margin: 0 auto; /* Center content container */
  padding: 20px;
}

.heading-container {
  text-align: left; /* Align heading to the left */
  margin-bottom: 20px;
}

.about-me-heading {
  font-size: 4rem; /* Adjust font size as needed */
  margin-bottom: 15px;
}

.profile {
  display: flex;
  gap: 20px; /* Space between image and info */
  align-items: flex-start; /* Align items to the top */
}

.image-container {
  width: 300px; /* Adjust this value to change the width */
}

img {
  width: 100%; /* Image takes up full width of container */
  border-radius: 10px; /* Add rounded corners */
}

.info-container {
  flex: 1; /* Take up remaining space */
  color: black;
}

.info {
  text-align: justify; /* Justify the text */
}

.options {
  display: flex;
  justify-content: center; /* Center the buttons */
  gap: 10px;
  margin-top: 20px; /* Add some spacing above the options */
}

.options button {
  background-color: #af855c;
  color: black;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

.options button.active {
  background-color: #ECDFCC; /* Highlight active button */
}

.section-container {
  background-color: #af855c;
  padding: 20px;
  border-radius: 10px;
  margin-top: 20px; /* Add some spacing above the section */
}

.skills-info, .education-info {
  text-align: left; /* Align text to the left */
}

.skills-info h3, .education-info h3 {
  margin-bottom: 10px;
}

.skill-item {
  margin-bottom: 15px;
}

.skill-item h4 {
  margin-bottom: 5px;
}

.skills, .education {
  list-style: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap; /* Allow skills to wrap if needed */
  gap: 10px;
  justify-content: flex-start; /* Align content to the left */
}

.skills li, .education li {
  background-color: #3C3D37;
  padding: 8px 15px;
  border-radius: 5px;
  color: #ECDFCC;
}

.education-item {
  margin-bottom: 15px;
}

.education-item p {
  margin-bottom: 5px;
}

/* Responsive Styling */
@media (max-width: 650px) {
  .about-me {
    padding: 2rem;
  }

  .profile {
    flex-direction: column;
    gap: 1rem;
  }

  .image-container {
    width: 100%;
  }

  .info-container {
    flex: 1;
  }

  .options {
    display: flex;
    justify-content: center; /* Center the buttons */
    gap: 10px;
    margin-top: 20px; /* Add some spacing above the options */
  }

  .section-container {
    width: 100%;
  }

  .skills, .education {
    flex-direction: column;
    gap: 0.5rem;
  }

  .skills li, .education li {
    width: 100%;
  }

  img {
    width: 80%; /* Adjust image width as needed */
    height: auto;
    border-radius: 10px; /* Add rounded corners */
  }

  .info-container p {
    text-align: justify; /* Justify text in info container */
  }

  .options {
    margin-bottom: 2rem; /* Add margin below options */
  }
}

.main-container {
  width: 100%;
}
</style>