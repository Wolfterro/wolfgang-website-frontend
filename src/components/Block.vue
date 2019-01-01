<template>
    <div class="main-content" v-bind:style="{ background: '#' + api.background_color }">
        <div class="container">
            <div class="row">
                <!-- Texto -->
                <div class="col-md-6">
                    <div class="main-content-inside-content">
                        <h1 class="main-content-h1">{{ api.title }}</h1>

                        <p v-html="api.content"></p>

                        <div class="indexsheet-main-content-button" v-if="api.button != null">
                            <a :href="api.button.link" target="_blank">
                                <button type="button" :class="api.button.type + ' ' + api.button.size"><span :class="api.button.left_icon"></span> {{api.button.text}} <span :class="api.button.right_icon"></span></button>
                            </a>
                        </div>
                    </div>
                </div>
                
                <!-- Imagem -->
                <div class="col-md-6">
                    <div class="main-content-inside-content-image">
                        <img :src="api.image" class="img-thumbnail" alt="Imagem">
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Block",
    props: {
        api: Object
    },
}
</script>

<style scoped>
.main-content {
    height: auto;
}

.main-content-inside-content {
    display: inline-block;
    margin: 100px auto;
    animation: fadein 3s;
}

.main-content-inside-content-image {
    display: inline-block;
    text-align: right;
    margin: 100px auto;
    animation: fadein 2s;
}

.main-content-image-transparent {
    background: transparent;
    border: none;
}

.main-content-h1 {
    color: white;
    font-family: 'Work Sans',  Arial, Helvetica, sans-serif;
    font-size: 38px;
    font-weight: bold;
    margin-bottom: 30px;
}

p {
    color: white;
    font-family: 'Work Sans',  Arial, Helvetica, sans-serif;
    font-size: 19px;
}

.main-content-button {
    margin-top: 30px;
}

@media (max-width: 767px) {
    /* Main Content */
    .main-content-inside-content-image {
        text-align: center;
        margin-top: -20px;
    }

    .main-content-button {
        text-align: center;
    }
}

/* Animations */
@keyframes fadein {
    from { opacity: 0; }
    to   { opacity: 1; }
}
</style>
