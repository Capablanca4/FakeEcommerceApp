<template>
   <footer class="footer">
    <div class="footer__column">
        <h4>Get to know me</h4>
        <nuxt-link to="/KnowMe"> 
            Me
        </nuxt-link>
        <nuxt-link to="/KnowMe/blog"> 
            My blog
        </nuxt-link>
        <nuxt-link to="/KnowMe/contactMe"> 
            Contact me
        </nuxt-link>
    </div>
    <div class="footer__column">
        <h4>This Site</h4>
        <nuxt-link to="/Site/why"> 
            Why
        </nuxt-link>
        <nuxt-link to="/Site/how"> 
            How
        </nuxt-link>
        <nuxt-link to="/Site/help"> 
            Help
        </nuxt-link>
    </div>
   </footer> 
</template>

<script>
export default {
    
}
</script>

<style lang="scss" scoped>

@import './assets/sass/variables';

.footer{
    height: height(footer);
    width: 100%;
    background-color: color("blue");
    display: flex;
    justify-content: space-evenly;
    position: absolute;
    bottom: -height(footer);

    &__column{
        display: flex;
        flex-direction: column;
        color: white;
        margin: 2em;

        & > *{
            margin-bottom: 4px;
        }
    }
}

a{
    color: rgba(255, 255, 255, 0.7);
    text-decoration: none;

    &:hover{
        text-decoration: underline;
    }
}
</style>