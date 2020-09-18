<template>
<div class="min-h-screen lg:max-w-screen-lg lg:mx-auto">
    <app-user-details :data="userData"></app-user-details>
    <app-user-experience :data="userExperience"></app-user-experience>
    <div class="lg:flex">
        <app-user-skills class="lg:w-1/2" :data="userSkills"></app-user-skills>
        <app-user-blogs class="lg:w-1/2 lg:w-full" :data="userBlogs"></app-user-blogs>
    </div>
        <app-user-hobbies :data="userHobbies"></app-user-hobbies>
</div>
</template>

<script>
export default {
    name: "Index",
    components: {
        'appUserDetails': () => import('@/components/UserDetails'),
        'appUserSkills': () => import('@/components/UserSkills'),
        'appUserExperience': () => import('@/components/UserExperience'),
        'appUserBlogs': () => import('@/components/UserBlogs'),
        'appUserHobbies': () => import('@/components/UserHobbies'),
    },
    data() {
        return {
            userData: {
                profilePhoto: 'nisarg/kunkka.png',
                name: 'Nisarg Patel',
                position: 'Full Stack Web Developer',
                email: 'nisargp42@gmail.com',
                phone: '+1-(306)-596-2654',
                bio: `
                <p>I am a Full Stack web developer with industry experience building websites and web applications. I specialize in Laravel, SQL and Javascript.</p>
                `,
            },
            //Level out of 100
            userSkills: [{
                    name: 'Javascript',
                    level: 80
                },
                {
                    name: 'CSS',
                    level: 80
                },
                {
                    name: 'HTML',
                    level: 80
                },
                {
                    name: 'Vue.js',
                    level: 70
                },
                {
                    name: 'Vuex',
                    level: 60
                },
                {
                    name: 'Laravel',
                    level: 70
                },
                {
                    name: 'SQL',
                    level: 70
                },
            ],
            userExperience: [{
                    companyLogo: 'nisarg/desystems.png',
                    companyName: 'D.E.Systems',
                    duration: 'Dec 2019 - Present',
                    position: 'Web Developer',
                    description: `
                    <p>Responsible for creating responsive and efficient web designs using technologies like HTML,SCSS & Vue.js.</p>
                    <p>To create a library of reusable UI components which can used across different product...</p>`,
                },
                {
                    companyLogo: 'nisarg/nokia.png',
                    companyName: 'Nokia',
                    duration: 'Apl 2019 - Aug 2019',
                    position: 'Learning Services Developer : Internship',
                    description: `
                    <p>Write well designed, testable, efficient code by using best software development practices</p>
                    <p>Developed an exam grading system with Bootstrap, CSS and jQuery as front-end and Perl and SQL as back-end technologies.</p>
                    <p>Developed a user-interactive learning management system with Bootstrap, CSS and jQuery as front-end and Perl and SQL as back-end technologies...</p>`,
                },
                {
                    companyLogo: 'nisarg/nokia.png',
                    companyName: 'Nokia',
                    duration: 'Jan 2018 - Jan 2019',
                    position: 'Learning Services Developer : Internship & Part Time',
                    description: `
                    <p>Used Scrum Agile Methodology in my work (Daily Scrum Meeting, Planning Poker, Sprint Backlog, 1on1 meeting)</p>
                    <p>Create website layout/user interface by using standard HTML/CSS practices</p>
                    <p>Integrate data from various back-end services and databases</p>
                    <p>Gather and refine specifications and requirements based on technical needs</p>
                    <p>Cooperate with web designers to match visual design intent</p>
                    <p>Create and maintain software documentation...</p>
                    `,
                }
            ],
            userBlogs: [{
                title: `How to structure your API's in a Vue.js environment.`,
                blogBanner: 'nisarg/blog.png',
                description: `
                    <p>Placeholder Blog data</p>
                    <p>I am using axios as HTTP client for making api calls, I have created a gateways folder in my src folder and I have put files for each backend, creating axios instances, like following.</p>
                    <p class="m-4"></p>
                    <p>If you are maintaining product related data in a dedicate vuex module, you can dispatch an action from the method in component, which will internally call the backend API and populate data in the store, code will look something like following...</p>
                    `,
            }],
            userHobbies : [
                {
                    title : 'Gaming',
                    photo : 'nisarg/gaming.jpg',
                    description : 'Multiplayer games like DOTA2,COD,Rocket League...'
                },
                {
                    title : 'Guitar,Music & Podcasts',
                    photo : 'nisarg/guitar.jpg',
                    description : 'Definitely not a pro at playing guitar yet ! But can play few beautiful sounding melodies😆'
                },
                {
                    title : 'Learning/Programming',
                    photo : 'nisarg/learning.jpg',
                    description : 'Always learning on how I can improve my design thinking and practices'
                },
            ]
        }
    }
}
</script>

<style lang="scss" scoped>

</style>
