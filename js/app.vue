const { 
    createApp, 
    ref 
} = Vue;

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

        const toggleActive = (skill) => {
            skill.active = !skill.active;
        };

        return {
            skills,
            socialLinks,
            toggleActive
        };
    },
    mounted() {
        const setViewportHeight = () => {
            const vh = window.innerHeight * 0.01;
            document.documentElement.style.setProperty('--vh', `${vh}px`);
        };

        setViewportHeight();
        window.addEventListener('resize', setViewportHeight);
    }
}).mount('#app');