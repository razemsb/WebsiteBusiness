const { createApp } = Vue;

createApp({
    data() {
        return {
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
                { name: 'razemsb (me)' },
                { name: 'Kamikaze236' },
                { name: 'ratPunk' },
                { name: 'AutiDarkness' },
                { name: 'Minat0_Sensei' },
                { name: 'Lagger125' },
                { name: 'L1M1IT' }
            ],
            groups: [
                {
                    name: "Development Team",
                    icon: "bi-code-square",
                    description: "Core development team working on main projects",
                    members: ["Kamikaze236", "ratPunk", "AutiDarkness", "Lagger125", "L1M1IT"],
                    roles: ["Lead Developer", "UI/UX Designer"],
                    technologies: ["Vue.js", "PHP", "Bootstrap", "MySQL"],
                    achievements: ["Launched 5+ projects", "Optimized performance by 40%"]
                },
                {
                    name: "Design Collective",
                    icon: "bi-palette",
                    description: "Creative team responsible for visual design",
                    members: ["DesignMaster", "PixelArtist", "UXWizard"],
                    roles: ["UI Consultant"],
                    technologies: ["Figma", "Adobe XD", "Photoshop"]
                },
                {
                    name: "Open Source Contributors",
                    icon: "bi-github",
                    description: "Group collaborating on open source projects",
                    members: ["Dev1", "Dev2", "Dev3"],
                    roles: ["Maintainer", "Code Reviewer"],
                    technologies: ["JavaScript", "PHP", "Vue.js"],
                    achievements: ["Nothing :("]
                }
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
        },
        toggleGroup(index) {
            this.expandedGroup = this.expandedGroup === index ? null : index;
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