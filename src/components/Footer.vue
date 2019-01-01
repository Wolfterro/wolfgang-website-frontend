<template>
    <div class="footer">
        <div class="container">
            <div class="row">
                <div class="col-md-12">
                    <div class="footer-content">
                        <p class="footer-p">- {{ api.info.owner }} -</p> 
                        <h1 class="footer-h1">{{ api.info.occupation }}</h1>
            
                        <hr class="footer-hr">
            
                        <h2 class="footer-h2">{{ api.info.additional_info }}</h2>

                        <p class="footer-social-media-p"><a class="footer-a" v-bind:href="api.social_media.linkedin" target="_blank" >LinkedIn</a> • <a class="footer-a" v-bind:href="api.social_media.github" target="_blank">GitHub</a> • <a class="footer-a" v-bind:href="'mailto:' + api.social_media.email">E-Mail</a></p>
                        
                        <p class="footer-social-media-p">© 2018 Wolfgang de Almeida Pires. Todos os direitos reservados.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Footer",
    props: {
        api: Object
    }
}
</script>

<style scoped>
/* Footer Content */
.footer {
    height: auto;
    background: #212121;
}

.footer-content {
    display: block;
    margin: 20px;
    text-align: center;
    animation: fadein 2s;
}

.footer-h1 {
    color: white;
    font-family: 'Work Sans',  Arial, Helvetica, sans-serif;
    font-size: 24px;
    font-weight: bold;
}

.footer-p {
    color: white;
    font-family: 'Work Sans', Arial, Helvetica, sans-serif;
    font-size: 12px;
}

.footer-hr {
    background: #03a9f4;
    width: 50%;
    height: 2px;
    border: 1px solid #212121;
    border-radius: 15px;
}

.footer-h2 {
    color: white;
    font-family: 'Work Sans',  Arial, Helvetica, sans-serif;
    font-size: 16px;
}

.footer-social-media-p {
    color: white;
    font-family: 'Work Sans',  Arial, Helvetica, sans-serif;
    font-size: 12px;
    margin-top: 15px;
}

.footer-a, a:link, a:visited, a:hover, a:active {
    color: white;
    text-decoration: none;
}

/* Animations */
@keyframes fadein {
    from { opacity: 0; }
    to   { opacity: 1; }
}
</style>
