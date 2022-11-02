<template>
    <section>
        <div class="row justify-content-center">
            <div class="col-12 col-sm-10">
                <div class="card text-center px-5 py-5">
                    <img id="profile-avatar" class="img-fluid img-profile rounded-circle mb-2 mx-auto d-block" :src="avatar" alt="avatar" width="250px" height="250px">
                    <div class="mb-3">
                        <h1 class="mb-2">{{ fullname }}</h1>
                        <h4 class="mb-2">{{ occupation }}</h4>
                        <p>{{ short_description }}</p>
                    </div>
                    <div>
                        <Linkedin v-bind:link="linkedin"/>
                        <Github v-bind:link="github" />
                    </div>
                </div>
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