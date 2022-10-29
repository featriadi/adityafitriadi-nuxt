<template>
    <section>
        <Navbar />
        <Nuxt />
        <Footer />
    </section>
</template>

<script>
    import Navbar from "@/components/headers/Navbar.vue";
    import Footer from "@/components/headers/Footer.vue";

    export default {
        components: {
            Navbar,
            Footer
        }
    }
</script>