const { createApp, ref } = Vue;

createApp({
    setup() {
        const skills = ref([
            { name: 'HTML5', icon: 'html-5.png', active: false },
            { name: 'CSS3', icon: 'css-3.png', active: false },
            { name: 'Bootstrap', icon: 'bootstrap.png', active: false },
            { name: 'JavaScript', icon: 'js.png', active: false },
            { name: 'Vue.js', icon: 'vue.png', active: false },
            { name: 'PHP', icon: 'php.png', active: false },
            { name: 'SQL', icon: 'mysql.png', active: false }
        ]);

        const socialLinks = ref([
            { name: 'GitHub', url: 'https://github.com/razemsb', icon: 'github' },
            { name: 'Telegram', url: 'https://t.me/razemsb', icon: 'telegram' }
        ]);

        const languageStats = ref([
            { name: 'HTML', percentage: 25, color: '#e34c26' },
            { name: 'CSS', percentage: 20, color: '#2965f1' },
            { name: 'JavaScript', percentage: 30, color: '#f0db4f' },
            { name: 'PHP', percentage: 15, color: '#787cb5' },
            { name: 'Other', percentage: 10, color: '#41b883' }
        ]);

        const toggleActive = (skill) => {
            skill.active = !skill.active;
        };

        return {
            skills,
            socialLinks,
            languageStats,
            toggleActive
        };
    },
}).mount('#app');