<template>
    <section>
        <div class="card justify-content-center text-center px-5 py-5">
            <img id="profile-avatar" class="img-fluid img-profile rounded-circle mb-2 mx-auto d-block" :src="avatar" alt="avatar" width="250px" height="250px">
            <h1 class="mb-0">{{ fullname }}</h1>
            <h3 class="mb-2">{{ occupation }}</h3>
            <h5>{{ short_description }}</h5>
            <div class="mt-3">
                <Linkedin v-bind:link="linkedin"/>
                <Github v-bind:link="github" />
            </div>
        </div>
    </section>
</template>

<script>
    import Linkedin from "@/components/icons/Linkedin.vue"
    import Github from "@/components/icons/Github.vue";

    export default {
        name: 'ProfileComponent',
        props: [
            'dataSet',
        ],
        components: {
            Linkedin,
            Github,
        },
        data() {
            return {
                profile: this.dataSet,
                fullname: this.dataSet.fullname,
                occupation: this.dataSet.occupation,
                short_description: this.dataSet.short_description,
                avatar: `${ process.env.BASE_API_URL }/${ this.dataSet.avatar }`,
                linkedin: this.dataSet.linkedin_url,
                github: this.dataSet.github_url,
            }
        },
    }
</script>