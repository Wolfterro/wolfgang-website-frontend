<template>
    <div class="jumbotron jumbotron-fluid text-center main-jumbotron" v-bind:style="{ backgroundImage: jumbotronCSS + this.api.info.jumbotron_image + ')'}">
        <div class="container">
            <div class="main-jumbotron-text">
                <p class="jumbotron-p">- {{ api.info.owner }} -</p> 
                <h1 class="jumbotron-h1">{{ api.info.occupation }}</h1>

                <hr class="jumbotron-hr">

                <h2 class="jumbotron-h2">{{ api.info.additional_info }}</h2>

                <div class="jumbotron-social-media-div">
                    <a v-bind:href="api.social_media.linkedin" target="_blank" ><i class="fab fa-linkedin-in fa-icon-light"></i></a>
                    <a v-bind:href="api.social_media.github" target="_blank"><i class="fab fa-github fa-icon-light"></i></a>
                    <a v-bind:href="'mailto:' + api.social_media.email"><i class="fas fa-at fa-icon-light"></i></a>
                </div>
            </div> 
        </div>
    </div>
</template>

<script>
export default {
    name: "Jumbotron",
    props: {
        api: Object
    },
    data () {
        return {
            jumbotronCSS: null
        }
    },
    created () {
        this.jumbotronCSS = 'linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), url('
    }
}
</script>

<style scoped>
.main-jumbotron {
    height: 600px;
    background-size: cover;
    background-color: #212121;
    margin-bottom: auto;
}

.main-jumbotron-text {
    display: block;
    margin: 100px auto;
    animation: fadein 2s;
}

.jumbotron-h1 {
    color: white;
    font-family: 'Work Sans', Arial, Helvetica, sans-serif;
    font-weight: bold;
    font-size: 48px;
}

.jumbotron-h2 {
    color: white;
    font-family: 'Work Sans',  Arial, Helvetica, sans-serif;
    font-size: 36px;
}

.jumbotron-p {
    color: white;
    font-family: 'Work Sans', Arial, Helvetica, sans-serif;
    font-size: 24px;
}

.jumbotron-hr {
    background: #03a9f4;
    width: auto;
    height: 2px;
    border: 1px solid #212121;
    border-radius: 15px;
}

.jumbotron-social-media-div {
    display: inline-block;
    margin-top: 25px;
    animation: fadein 2s;
}

.jumbotron-social-media-div i {
    margin-left: 20px;
}

.fa-icon-light {
    color: #fff;
    font-size: 38px;
}

@media (max-width: 767px) {
    /* Jumbotron Content */
    .main-jumbotron {
        height: 450px;
    }

    .main-jumbotron-text {
        margin-top: 50px;
    }

    .jumbotron-h1 {
        font-size: 24px;
    }

    .jumbotron-h2 {
        font-size: 18px;
    }

    .jumbotron-p {
        font-size: 12px;
    }
}

/* Animations */
@keyframes fadein {
    from { opacity: 0; }
    to   { opacity: 1; }
}
</style>
