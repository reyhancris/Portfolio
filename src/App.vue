<template>
  <div class="portfolio">
    <header class="navbar">
      <nav>
    <ul>
      <li><a href="#" @click="scrollToSection($event, 'home')">Home</a></li>
      <li><a href="#" @click="scrollToSection($event, 'about')">About</a></li>
      <li><a href="#" @click="scrollToSection($event, 'my-work')">My Work</a></li>
      <li><a href="#" @click="scrollToSection($event, 'my-services')">My Services</a></li>
      <li><a href="#" @click="scrollToSection($event, 'contact')">Contact Us</a></li>
    </ul>
  </nav>

    </header>
    <aside class="sidebar">
      <!-- Profile Box with Gray Background -->
      <div class="profile-box">
        <img :src="profileImage" alt="Profile Image" class="profile-image" />
        <h2>Reyhan Cris M. Florida</h2>
        <p>Front-end Developer<br />UI/UX Designer</p>
      </div>

      <div class="profile-details">
        <div class="location">
          <p><strong>Nationality:</strong> Filipino</p>
          <p><strong>City:</strong> Butuan</p>
          <p><strong>Age:</strong> 20</p>
        </div>

        <!-- Language Skills Section with Doughnut Chart -->
        <div class="language-skills">
          <h3>Languages</h3>
          <div v-for="(language, index) in languages" :key="index" class="skill">
            <p>{{ language.name }}: <span class="percent">{{ language.level }}%</span></p>
            
            <!-- Doughnut Chart for Language Proficiency -->
            <div class="doughnut-container">
              <Doughnut :data="getChartData(language.level)" :options="chartOptions" />
            </div>
          </div>
        </div>

        <!-- Tech Skills Section with Bar Graph -->
        <div class="tech-skills">
          <h3>Technical Skills</h3>
          <div v-for="(techSkill, index) in techSkills" :key="index" class="skill">
            <p>{{ techSkill.name }}: <span class="percent">{{ techSkill.level }}%</span></p>
            <div class="skill-bar">
              <div 
                class="skill-bar-fill" 
                :style="{ width: techSkill.level + '%', backgroundColor: techSkill.level >= 80 ? '#FFD700' : '#666' }"
              ></div>
            </div>
          </div>
        </div>
      </div>
    </aside>

  
    <main id="home" class="content">
  <header class="hero">
    <h1>Discover my Amazing Art Space!</h1>
    <p class="tagline">I build automation tools and design digital experiences.</p>
  </header>


      <!-- About Section -->
      <section id="about" class="about">
        <h2>About Me</h2>
        <p>
          Hello! I'm Reyhan Cris M. Florida, a passionate front-end developer and UI/UX designer. 
          With a strong background in creating seamless digital experiences, I specialize in building 
          responsive websites, user-friendly interfaces, and crafting engaging designs that meet both 
          functional and aesthetic requirements. My work combines creativity and technical skills to 
          bring innovative ideas to life.
        </p>
      </section>

      <section class="stats">
        <div class="stat">
          <h3>10+</h3>
          <p>Years Experience</p>
        </div>
        <div class="stat">
          <h3>143</h3>
          <p>Completed Projects</p>
        </div>
        <div class="stat">
          <h3>114</h3>
          <p>Happy Customers</p>
        </div>
        <div class="stat">
          <h3>20+</h3>
          <p>Honors and Awards</p>
        </div>
      </section>

       <!-- My Work Section -->
       <section id="my-work" class="my-work">
        <h2>My Work</h2>
        <div class="work-items">
          <div class="work-item">
            <img src="@/assets/work1.jpg" alt="Work 1" class="work-image" />
            <h3>Reycord Studio</h3>
            <p>Editor-In-Chief and owner of Reycord Studio, a Facebook page dedicated to freelance photography and videography. This platform is where I showcase my passion for visual storytelling, capturing moments that matter. Join me as I continue to explore the art of photography and videography, bringing creativity to life through every frame..</p>
          </div>
          <div class="work-item">
            <img src="@/assets/work2.jpg" alt="Work 2" class="work-image" />
            <h3>Reycreation</h3>
            <p>Editor-In-Chief and owner of Reycreation, my personal page dedicated to freelance graphics design. This platform is where I showcase my passion for visual creativity, bringing designs to life with every project. Join me as I explore the art of design and innovation, crafting unique and compelling visuals that tell a story..</p>
          </div>
          <div class="work-item">
            <img src="@/assets/work3.png" alt="Work 3" class="work-image" />
            <h3>Front-ReyEnd</h3>
            <p>As the creator and lead designer at Front-ReyEnd, I bring my front-end development skills to life with a focus on crafting visually stunning, user-friendly websites. This platform is where I combine creativity and code, building seamless interfaces that not only look beautiful but work flawlessly. Join me on my journey as I push the boundaries of web design, creating responsive, interactive, and engaging web experiences that leave a lasting impression. Let’s make the web a more beautiful place, one pixel at a time..</p>
          </div>
        </div>
      </section>

      <!-- My Services Section -->
      <section id="my-services" class="my-services">
        <h2>My Services</h2>
        <div class="service-items">
          <div class="service-item">
            <h3>Web Development</h3>
            <p>Crafting responsive, modern websites tailored to your needs.</p>
          </div>
          <div class="service-item">
            <h3>Photography / Videography</h3>
            <p>Creating captivating visuals and immersive storytelling through photography and videography..</p>
          </div>
          <div class="service-item">
            <h3>Graphics Design</h3>
            <p>Creating stunning visuals and branding materials.</p>
          </div>
        </div>
      </section>

<!-- Contact Us Section -->
<section id="contact" class="contact-us">
  <h2>Contact Us</h2>
  <p>I'd love to hear from you! Whether it's a project, a question, or just to say hello, feel free to get in touch with me.</p>
  
  <div class="contact-details">
    <div class="contact-item">
      <h3>Email</h3>
      <p><a href="mailto:reyhancris@gmail.com">reyhancris@gmail.com</a></p>
    </div>
    <div class="contact-item">
      <h3>Phone</h3>
      <p><a href="tel:+639123456789">+63 912 345 6789</a></p>
    </div>
    <div class="contact-item">
      <h3>Social Media</h3>
      <p>
        <a href="https://www.facebook.com/reyhancrisflorida" target="_blank">Facebook</a> 
      </p>
    </div>
  </div>

  <!-- Contact Form -->
  <form class="contact-form">
    <label for="name">Enter your name</label>
    <input type="text" id="name" placeholder="Your Name" required>

    <label for="email">Enter a valid email address</label>
    <input type="email" id="email" placeholder="Your Email" required>

    <label for="message">Enter your message</label>
    <textarea id="message" rows="4" placeholder="Your Message" required></textarea>

    <button type="submit">Submit</button>
  </form>
</section>


    
    </main>
  </div>
</template>

<script>
import { Doughnut } from 'vue-chartjs';
import { defineComponent } from 'vue';
import { Chart as ChartJS, Title, Tooltip, Legend, ArcElement } from 'chart.js';

// Register necessary components from Chart.js
ChartJS.register(Title, Tooltip, Legend, ArcElement);

export default defineComponent({
  name: 'MyPortfolio',
  components: {
    Doughnut,
  },
  data() {
    return {
      profileImage: require('@/assets/id.jpg'), // Adjust path if needed
      languages: [
        { name: 'English', level: 80 },
        { name: 'Filipino', level: 90 },
      ],
      techSkills: [
        { name: 'HTML', level: 80 },
        { name: 'CSS', level: 85 },
        { name: 'JavaScript', level: 80 },
        { name: 'Graphics Design', level: 85 },
        { name: 'Photography', level: 90 },
        { name: 'Videography', level: 80 },
      ],
      chartOptions: {
        responsive: true,
        maintainAspectRatio: true,
        plugins: {
          legend: {
            display: false,
          },
          tooltip: {
            enabled: false,
          },
        },
        cutout: '70%', // Adjust this to control the thickness of the ring
      },
    };
  },
  methods: {
    getChartData(level) {
      return {
        labels: ['Progress', 'Remaining'],
        datasets: [
          {
            data: [level, 100 - level],
            backgroundColor: ['#FFD700', '#444'],
            borderWidth: 1,
          },
        ],
      };
    },
    scrollToSection(event, sectionId) {
      event.preventDefault(); // Prevent default anchor behavior

      const target = document.getElementById(sectionId);
      if (target) {
        target.scrollIntoView({
          behavior: 'smooth',
          block: 'start',
        });
      }
    }
  },
});
</script>



<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

html {
  scroll-behavior: smooth;
}


.navbar {
  background-color: #000; /* Black background */
  padding: 1rem 2rem;
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 1000;
}

.navbar nav ul {
  display: flex;
  justify-content: center;
  list-style: none;
  margin: 0;
  padding: 0;
}

.navbar nav ul li {
  margin: 0 1rem;
}

.navbar nav ul li a {
  font-family: 'Nunito', Arial, sans-serif;
  font-size: 1.3rem;
  font-weight: bold;
  color: #fff; /* White text */
  text-decoration: none;
  transition: color 0.3s, transform 0.3s;
}

.navbar nav ul li a:hover {
  color: #FFD700; /* Golden color on hover */
  transform: scale(1.1);
}


body {
  font-family: 'Canva Sans', Arial, sans-serif;
  background: #000;
  color: #fff;
  margin: 0;
  padding: 0;
  display: flex;
  overflow-x: hidden;
}

p {
  font-family: 'Roboto', Arial, sans-serif;
}


.portfolio {
  display: flex;
  flex-wrap: nowrap;
  padding-top: 4rem; /* Adjust for fixed navbar */

}

.sidebar {
  width: 700px;
  background-color: #111;
  color: #bbb;
  padding: 3rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  box-shadow: 2px 0 5px rgba(255, 255, 255, 0.1);
  transition: background-color 0.3s;
}

.profile-box {
  background-color: #333;
  color: #fff;
  width: 80%;
  padding: 2.3rem;
  text-align: center;
  border-radius: 8px;
  margin-bottom: 1rem;
}

.profile-image {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  margin-bottom: 0.5rem;
  border: 3px solid #fff;
  transition: transform 0.3s ease;
}

.profile-image:hover {
  transform: scale(1.1);
}

h2 {
  color: #fff;
  font-size: 1.5rem;
  margin: 0.5rem 0;
  font-family: 'Nunito', Arial, sans-serif;
}

h3 {
  color: #fff;
  font-size: 1.5rem;
  margin: 0.5rem 0;
  font-family: 'Nunito', Arial, sans-serif;
}

.profile-details {
  width: 100%;
}

.location p {
  font-size: 0.9rem;
  margin: 0.5rem 0;
  font-family: 'Nunito', Arial, sans-serif;
  font-weight: bold;
  color: #fff; /* White text */
}

.language-skills, .tech-skills {
  width: auto;
  margin-top: 1rem;
  background-color: #333;
  color: #fff;
  padding: 2.3rem; /* Match padding with .profile-box */
  text-align: center;
  border-radius: 8px;
  margin-bottom: 1rem;
}


.percent {
  color: #fff;
  font-weight: bold;
}

.skill {
  margin-bottom: 1rem;
}

.doughnut-container {
  width: 80px; /* Fixed size */
  height: 80px; /* Fixed size */
  margin-top: 1rem;
  display: inline-block; /* Prevent moving */
}

.skill-bar {
  width: 100%;
  height: 10px;
  background-color: #333;
  border-radius: 5px;
  overflow: hidden;
  margin-top: 5px;
}

.skill-bar-fill {
  height: 100%;
  transition: width 0.5s ease;
  border-radius: 5px 0 0 5px;
}

.content {
  flex-grow: 1;
  padding: 1rem;
}

.hero {
  text-align: left;
  padding: 4rem 5rem;
  background-image: url('@/assets/bg.jpg');
  background-size: cover;
  background-position: center;
  border-radius: 10px;
  margin-bottom: 1rem;
  text-align-last: left;
  color: #fff;
  box-shadow: 0 4px 15px rgba(255, 255, 255, 0.1);
}

.hero h1 {
  font-size: 2.5rem;
  font-weight: 700;
  font-family: 'Nunito', Arial, sans-serif;
  color:rgb(255, 215, 0)
}

.tagline {
  font-size: 1.2rem;
  margin: 1rem 0;
}

.cta-button {
  padding: 0.7rem 2rem;
  background-color: rgb(255, 215, 0);
  color: #000;
  border: none;
  border-radius: 25px;
  font-size: 1rem;
  font-family: 'Nunito', Arial, sans-serif;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
}

.cta-button:hover {
  background-color: #ccc;
  transform: scale(1.05);
  font-family: 'Nunito', Arial, sans-serif;
}

.stats {
  display: flex;
  justify-content: space-around;
  background-color: #222;
  padding: 1rem;
  border-radius: 10px;
  margin-bottom: 1rem;
  text-align: center;
}

.stat {
  color: #fff;
  transition: color 0.3s;
}

.stat h3 {
  margin: 0;
  font-size: 1.5rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: rgb(255, 215, 0);
}

.stat:hover {
  color: #bbb;
}

.about {
  padding: 1rem;
  background-color: #222;
  color: #fff;
  margin-bottom: 1rem;
  border-radius: 10px;
}

.about h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: rgb(255, 215, 0);
}

.about p {
  font-size: 1.1rem;
  line-height: 1.6;
  font-family: 'Roboto', Arial, sans-serif;
}

.my-services {
  padding: 2rem;
  background-color: #222;
  color: #fff;
  margin-bottom: 1rem;
  border-radius: 10px;
}

.my-services h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: rgb(255, 215, 0);
}

.service-items {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
}

.service-item {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  width: 30%;
}

.service-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(255, 255, 255, 0.2);
}

.service-item h3 {
  margin-bottom: 1rem;
  font-size: 1.5rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: rgb(255, 215, 0);
}

.service-item p {
  font-size: 1rem;
  font-family: 'Roboto', Arial, sans-serif;
  line-height: 1.5;
}

.contact-us {
  padding: 2rem;
  background-color: #222;
  color: #fff;
  margin-bottom: 1rem;
  border-radius: 10px;
}

.contact-us h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: rgb(255, 215, 0);
}

.contact-us p {
  font-size: 1rem;
  line-height: 1.5;
  margin-bottom: 2rem;
  color: white;

}

.contact-details {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
}

.contact-item {
  width: 30%;
  text-align: center;
}

.contact-item h3 {
  font-size: 1.5rem;
  color: #FFD700;
  margin-bottom: 0.5rem;
  font-family: 'Nunito', Arial, sans-serif;
}

.contact-item p {
  font-size: 1rem;
  line-height: 1.4;
  font-family: 'Roboto', Arial, sans-serif;
}

.contact-item a {
  color: #ffffff;
  text-decoration: none;
}

.contact-item a:hover {
  text-decoration: underline;
}

/* Contact Form Styling */
.contact-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  margin-top: 2rem;
}

.contact-form label {
  font-size: 0.9rem;
  color: #ddd;
}

.contact-form input,
.contact-form textarea {
  padding: 0.8rem;
  border-radius: 5px;
  border: 1px solid #ccc;
  font-size: 1rem;
  font-family: 'Roboto', Arial, sans-serif;
}

.contact-form input:focus,
.contact-form textarea:focus {
  outline: none;
  border-color: #FFD700;
}

.contact-form button {
  padding: 0.8rem 1.5rem;
  border: none;
  border-radius: 5px;
  background-color: #FFD700;
  color: #222;
  font-size: 1rem;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s;
}

.contact-form button:hover {
  background-color: #FFA500;
}

/* Adjust for responsiveness */
@media (max-width: 768px) {
  .contact-details {
    flex-direction: column;
    gap: 1rem;
  }

  .contact-item {
    width: 100%;
  }
}


.my-work {
  padding: 2rem;
  background-color: #222;
  color: #fff;
  margin-bottom: 1rem;
  border-radius: 10px;
}

.my-work h2 {
  font-size: 2rem;
  margin-bottom: 1rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: rgb(255, 215, 0);
}

.work-items {
  display: flex;
  justify-content: space-between;
  gap: 2rem;
}

.work-item {
  background-color: #333;
  color: #fff;
  padding: 1rem;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 4px 10px rgba(255, 255, 255, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  width: 30%;
}

.work-item:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(255, 255, 255, 0.2);
}

.work-image {
  width: 100%;
  height: auto;
  border-radius: 5px;
}

.work-item h3 {
  margin: 1rem 0;
  font-size: 1.2rem;
  font-family: 'Nunito', Arial, sans-serif;
  color: #FFD700;
}

.work-item p {
  font-size: 0.9rem;
  line-height: 1.4;
}

/* Responsive Styles */
@media (max-width: 768px) {
  .portfolio {
    flex-direction: column;
  }

  .sidebar {
    width: 100%;
  }

  .stats {
    flex-direction: column;
  }
}

 /* Footer Styling */
  .footer {
    padding: 1rem;
    background-color: #111;
    color: #bbb;
    text-align: center;
    font-size: 0.9rem;
    margin-top: 2rem;
  }

  .footer p {
    margin: 0;
  }

  .footer a {
    color: #FFD700;
    text-decoration: none;
    transition: color 0.3s;
  }

  .footer a:hover {
    color: #fff;
  }
</style>