const { createApp } = Vue;

createApp({
    data() {
        return {
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
            projects: [
                { 
                    name: 'FileManager', 
                    description: 'A modern file management system with Vue.js frontend and PHP API backend', 
                    technologies: ['Vue.js', 'PHP (API)', 'Bootstrap 5.3.3'],
                    githubUrl: 'https://github.com/razemsb/FileManager'
                },
                { 
                    name: 'WebPlayer', 
                    description: 'A web-based media player with playlist functionality and responsive design', 
                    technologies: ['Vue.js', 'PHP (API)', 'Bootstrap 5.3.3'],
                    githubUrl: 'https://github.com/razemsb/WebPlayer'
                }
            ]
        };
    },
    methods: {
        toggleActive(skill) {
            skill.active = !skill.active;
        }
    },
    mounted() {
        // Animate progress bars on mount
        setTimeout(() => {
            const progressBars = document.querySelectorAll('.progress-bar');
            progressBars.forEach(bar => {
                bar.style.width = bar.getAttribute('aria-valuenow') + '%';
            });
        }, 500);
    }
}).mount('#app');