<template>
  <div class="main-wrapper">
    <Navbar landing-link="#about" :navItems="navItems" id="sideNav"></Navbar>
    <div class="container-fluid p-0">
      <AboutMe :user="user" :social="social" id="about"></AboutMe>
      <Experience :experience="experience" id="experience"></Experience>
      <Education :education="education" id="education"></Education>
      <Skills
        :skills="skills"
        :responsibility="responsibility"
        id="skills"
      ></Skills>
      <Interests :interest="interest" id="interests"></Interests>
      <Awards :accomplishment="accomplishment" id="awards"></Awards>
    </div>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Skills from "./components/Skills.vue";
import Awards from "./components/Awards.vue";
import AboutMe from "./components/AboutMe.vue";
import Education from "./components/Education.vue";
import Interests from "./components/Interests.vue";
import Experience from "./components/Experience.vue";

export default {
  components: {
    Navbar,
    Skills,
    Awards,
    AboutMe,
    Education,
    Interests,
    Experience
  },
  data() {
    return {
      title: "My Portfolio",
      navItems: [
        { title: "About", link: "#about" },
        { title: "Experience", link: "#experience" },
        { title: "Education", link: "#education" },
        { title: "Skills", link: "#skills" },
        { title: "Interests", link: "#interests" },
        { title: "Awards", link: "#awards" }
      ],
      user: {
        name: "ANCHAL",
        surname: "SAHU",
        address: "Pune, Maharashtra 411057 · +91 96 91 95 38 51 ·",
        email: "anchalsahu@live.in",
        introduction:
          "Senior UI Developer | BA4, Currently working on technology which includes Node.JS, React.JS, Golang, ExpressJS, MongoDB, Docker, Kubernetes, Microservices, REST API etc."
      },
      social: [
        {
          name: "linkedin",
          url: "https://www.linkedin.com/in/anchalsahu/",
          icon: "fa-linkedin"
        },
        {
          name: "github",
          url: "https://github.com/anchalsahu",
          icon: "fa-github"
        }
      ],
      experience: [
        {
          position: "Senior UI Developer",
          company: "Barclays",
          description:
            "Working on technology which includes Node.JS, React.JS, Typescript, ExpressJS, Microservices, REST API etc",
          startDate: "Dec 2018",
          endDate: "Till Now"
        },
        {
          position: "Senior Software Engineer",
          company: "Ideavate Solutions Pvt. Ltd.",
          description:"",
          startDate: "March 2016",
          endDate: "Nov 2018"
        },
        {
          position: "Software Engineer",
          company: "Ideavate Solutions Pvt. Ltd.",
          description:"",
          startDate: "March 2012",
          endDate: "Feb 2016"
        }
      ],
      education: [
        {
          name: "Rajiv Gandhi Technological University",
          degree: "Bachelor of Engineering",
          stream: "Information Technology",
          marks: "",
          startDate: "Jul 2007",
          endDate: "Jul 2011"
        },
        {
          name: "Board of Secondary Education, Madhya Pradesh",
          degree: "Higher Secondary Certificate Examination",
          stream: "Maths, Physics, Chemistry, Biology",
          marks: "",
          startDate: "Jul 2006",
          endDate: "May 2007"
        },
        {
          name: "Board of Secondary Education, Madhya Pradesh",
          degree: "High School Certificate Examination",
          stream: "",
          marks: "",
          startDate: "Jul 2004",
          endDate: "May 2005"
        }
      ],
      skills: [
        {
          name: "javascript",
          icon: "devicons-javascript",
          level: "Proficient"
        },
        {
          name: "react",
          icon: "devicons-react",
          level: "Proficient"
        },
        {
          name: "nodejs",
          icon: "devicons-nodejs",
          level: "Proficient"
        },
        {
          name: "html",
          icon: "devicons-html5",
          level: "Proficient"
        },
        {
          name: "css3",
          icon: "devicons-css3",
          level: "Proficient"
        },
        
        {
          name: "ubuntu",
          icon: "devicons-ubuntu",
          level: "Upper Beginner"
        },
        
        {
          name: "git",
          icon: "devicons-git",
          level: "Proficient"
        },
        {
          name: "bitbucket",
          icon: "devicons-bitbucket",
          level: "Proficient"
        },
        {
          name: "jira",
          icon: "devicons-jira",
          level: "Upper Beginner"
        },
        
        {
          name: "jquery",
          icon: "devicons-jquery",
          level: "Proficient"
        },
        {
          name: "grunt",
          icon: "devicons-grunt",
          level: "Proficient"
        },
        {
          name: "gulp",
          icon: "devicons-gulp",
          level: "Proficient"
        },
        {
          name: "npm",
          icon: "devicons-npm",
          level: "Proficient"
        }
      ],
      responsibility: [
        {
          id: 1,
          text: "Cross Browser Testing & Debugging"
        },
        {
          id: 2,
          text: "Involvement in Recruitment Process"
        },
        {
          id: 3,
          text: "Agile Development & Scrum"
        },
        {
          id: 4,
          text: "Help Team Members whenever needed"
        },
        {
          id: 5,
          text: "Unit & Functional Testing"
        }
      ],
      interest:
        "Apart from being a web developer, I enjoy spending time with my family and friends. I love watching sci-fi, fantasy, comedy movies and web series, and I spend a large amount of my free time exploring the latest technolgy advancements in the front-end web development world.",
      accomplishment: [
        {
          id: 1,
          text: "Quarterly Appreciation Award",
          date: "Aug 2015",
          company: "Sigma Infosolutions Ltd"
        }  
      ]
    };
  },
  mounted() {
    const $ = this.jquery;
    this.$nextTick(() => {
      // our custom jQuery code goes here
      $('a.js-scroll-trigger[href*="#"]:not([href="#"])').click(function() {
        if (
          location.pathname.replace(/^\//, "") ===
            this.pathname.replace(/^\//, "") &&
          location.hostname === this.hostname
        ) {
          var target = $(this.hash);
          target = target.length
            ? target
            : $("[name=" + this.hash.slice(1) + "]");
          if (target.length) {
            $("html, body").animate(
              {
                scrollTop: target.offset().top
              },
              1000,
              "easeInOutExpo"
            );
            return false;
          }
        }
      });

      // Closes responsive menu when a scroll trigger link is clicked
      $(".js-scroll-trigger").click(function() {
        $(".navbar-collapse").collapse("hide");
      });

      // Activate scrollspy to add active class to navbar items on scroll
      $("body").scrollspy({
        target: "#sideNav"
      });
    });
  }
};
</script>

<style></style>
