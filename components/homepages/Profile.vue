<template>
    <section>
        <div class="card justify-content-center text-center py-5 px-5">
            <img id="profile-avatar" class="img-fluid img-profile rounded-circle mb-2 mx-auto d-block" :src="avatar" alt="avatar" width="250px" height="250px">
            <h1>{{ fullname }}</h1>
            <h4>{{ occupation }}</h4>
            <h5>{{ short_description }}</h5>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'ProfileComponent',
        props: [
            'dataSet',
        ],
        data() {
            return {
                profile: this.dataSet,
                fullname: this.dataSet.fullname,
                occupation: this.dataSet.occupation,
                short_description: `“${ this.dataSet.short_description }”`,
                avatar: `${ process.env.BASE_API_URL }/${ this.dataSet.avatar }`

            }
        },
    }
</script>