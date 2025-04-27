const { createApp } = Vue;

createApp({
  data() {
    return {
      currentSlide: 0,  // Текущий индекс слайда
      expandedGroup: null,
      socialLinks: [
        { name: 'GitHub', url: 'https://github.com/razemsb', icon: 'github' },
        { name: 'Telegram', url: 'https://t.me/razemsb', icon: 'telegram' },
        { name: 'Email', url: 'https://maxim1xxx363@gmail.com', icon: 'envelope' }
      ],
      skills: [
        { name: 'Vue.js', icon: 'vue.png', active: false },
        { name: 'PHP', icon: 'php.png', active: false },
        { name: 'Bootstrap', icon: 'bootstrap.png', active: false },
        { name: 'HTML5', icon: 'html-5.png', active: false },
        { name: 'CSS3', icon: 'css-3.png', active: false },
        { name: 'JavaScript', icon: 'js.png', active: false },
        { name: 'SQL', icon: 'mysql.png', active: false }
      ],
      languageStats: [
        { name: 'PHP', percentage: 45, color: '#787cb5' },
        { name: 'JavaScript', percentage: 30, color: '#f0db4f' },
        { name: 'HTML/CSS', percentage: 15, color: '#e34c26' },
        { name: 'SQL', percentage: 10, color: '#00758f' }
      ],
      Team: [
      { name: 'ratPunk', role: 'Full Stack Developer' },
      { name: 'AutiDarkness', role: 'Full Stack Developer' },
      { name: 'Lagger125', role: 'Frontend Developer' },
      { name: 'L1M1IT', role: 'Frontend Developer' },
      { name: 'Kamikaze236', role: '1С Developer', grade: 'TeamLid' },
      { name: 'Minat0_Sensei', role: 'GameDev' }
      ],
      groups: [
        {
          name: "Web Developers",
          icon: "bi-code-square",
          description: "Cool web developer",
          members: ["razemsb", "ratPunk", "AutiDarkness", "Lagger125", "L1M1IT"],
          roles: ["Web Developer", "UI/UX Designer"],
          technologies: ["Vue.js", "PHP", "Bootstrap", "MySQL"],
          achievements: ["Launched 4 projects", "Optimized performance by 40%"]
        }
      ],
      projects: [
        { 
          name: 'FileManager', 
          description: 'A modern file management system with Vue.js frontend and PHP API backend', 
          technologies: ['Vue.js', 'PHP (API)'],
          githubUrl: 'https://github.com/razemsb/FileManager'
        },
        { 
          name: 'WebPlayer', 
          description: 'A web-based media player with playlist functionality and responsive design', 
          technologies: ['Vue.js', 'Bootstrap 5.3.3'],
          githubUrl: 'https://github.com/razemsb/WebPlayer',
          webUrl: 'https://razemsb.github.io/WebPlayer/'
        },
        { 
          name: 'Hostix', 
          description: 'Website for website hosting', 
          technologies: ['Clean Code'],
          githubUrl: 'https://github.com/ratPunk/hostix',
          webUrl: 'https://ratpunk.github.io/hostix/'
        }
      ]
    };
  },
  methods: {
    toggleActive(skill) {
      skill.active = !skill.active;
    },
    toggleGroup(index) {
      this.expandedGroup = this.expandedGroup === index ? null : index;
    },
    nextSlide() {
      if (this.currentSlide < this.projects.length - 1) {
        this.currentSlide++;
      }
    },
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      }
    }
  },
  mounted() {
    setTimeout(() => {
      const progressBars = document.querySelectorAll('.progress-bar');
      progressBars.forEach(bar => {
        bar.style.width = bar.getAttribute('aria-valuenow') + '%';
      });
    }, 500);
  }
}).mount('#app');
