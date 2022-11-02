<template>
    <section class="container mt-4 mb-1">
        <Profile v-bind:dataSet="dataProfile"/>
    </section>
</template>

<script>
    import Axios from "axios";
    import Profile from "@/components/homepages/Profile.vue";

    export default {
        name: 'IndexPage',
        layout: 'main',
        components: {
            Profile
        },
        data() {
            return {
                dataProfile: this.$store.state?.DataProfile,
            }
        },
        async asyncData(context) {
            const { store } = context

            let configAPIProfile = {
                method: 'GET',
                url: `${ process.env.BASE_API_URL }/api/portofolio/profile`,
            }

            try {
                let getDataProfile = await Axios(configAPIProfile)
                store.commit('setDataProfile', getDataProfile.data.data)
            } catch (error) {
                console.log(error.message);
            }
        },
    }
</script>
