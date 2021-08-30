<template>
    <footer class="footerCon">

        <div class="wrapper">
            <div class="col">
                <nuxt-link to="/" aria-label="Go to the home page" class="logoImg"><img class="logoImg" src="@/assets/images/logo.svg" loading="lazy" decoding="async" alt="PlaylistTools.io"></nuxt-link>
                <p>PlaylistTools.io ©2021. All Rights Reserved.</p>
                <ul>
                    <li><nuxt-link to="#">ins</nuxt-link></li>
                    <li><nuxt-link to="#">fb</nuxt-link></li>
                    <li><nuxt-link to="#">twi</nuxt-link></li>
                </ul>
            </div>
        
            <nav class="footerNav" role="navigation">
                <ul>
                    <li class="title">Pages</li>
                    <li><nuxt-link to="/">Home</nuxt-link></li>
                    <li><nuxt-link to="#">Playlists</nuxt-link></li>
                    <li><nuxt-link to="#">Tracks</nuxt-link></li>
                    <li><nuxt-link to="#">Search</nuxt-link></li>
                    <li><nuxt-link to="/blogs">Blog</nuxt-link></li>
                </ul>
                <ul>
                    <li class="title">Usefull Links</li>
                    <li><nuxt-link to="#">Help</nuxt-link></li>
                    <li><nuxt-link to="#">About Us</nuxt-link></li>
                    <li><nuxt-link to="#">Privacy Policy</nuxt-link></li>
                    <li><nuxt-link to="#">Terms & Conditions</nuxt-link></li>
                    <li><nuxt-link to="#">Contact Us</nuxt-link></li>
                </ul>
                <ul>
                    <li class="title">Socials</li>
                    <li><nuxt-link to="#">Instagram</nuxt-link></li>
                    <li><nuxt-link to="#">Facebook</nuxt-link></li>
                    <li><nuxt-link to="#">Twitter</nuxt-link></li>
                </ul>
            </nav>
        </div>

    </footer>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    data() {
        return {
            

        }
    }
})
</script>

<style lang="scss" scoped>
.footerCon {
    border-top: 0.1rem solid #DDDDDD;
    margin-top: $sectionSpacing;
    content-visibility: auto;
    contain-intrinsic-size: 0 60rem;
    @include forBreakpoint(mobile tablet){
        margin-top: $mobTabSpacing;
    }
    .wrapper {
        @include wrapper;
        padding-top: 8rem;
        padding-bottom: 8rem;
        display: flex;
        justify-content: space-between;
        @include forBreakpoint(mobile tablet) {
            flex-wrap: wrap;
        }
        .col {
            min-width: 40rem;
            @include forBreakpoint(mobile tablet) {
                min-width: 100%;
                width: 100%;
            }
            .logoImg {
                height: 35px;
                width: 183.84px;
                margin-bottom: 3rem;
                transition: $animationSpeed;
                &:focus {
                    img {
                        transform: scale(1.1);
                    }
                }
                &:hover {
                    img {
                        transform: scale(1.1);
                    }
                }
            }
            p {
                @include body;
            }
            ul {
                margin-top: 1rem;
                display: flex;
                gap: 1rem;
                li {
                    a {
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        color: #fff;
                        font-weight: bold;
                        text-decoration: none;
                        height: 4rem;
                        width: 4rem;
                        min-width: 4rem;
                        background-color: lighten($accent1, 30%);
                        border-radius: 50%;
                        transition: $animationSpeed;
                        &:hover {
                            background-color: $accent1;
                        }
                        &:focus {
                            transform: scale(1.1);
                        }
                    }
                }
            }
        }
        .footerNav {
            width: 100%;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(8rem, 18rem));
            justify-content: end;
            gap: 2rem;
            @include forBreakpoint(mobile tablet) {
                justify-content: start;
                margin-top: 4rem;
                background-color: rgb(243, 243, 243);
                padding: 2rem;
                border-radius: 2rem;
            }
            ul {
                li {
                    padding: 0.5rem 0;
                    font-size: 1.6rem;
                    a {
                        text-decoration: none;
                        color: $bodyText;
                        position: relative;
                        &:focus, &:hover {
                            &::after {
                                content: '';
                                position: absolute;
                                left: 0;
                                bottom: -5px;
                                width: 100%;
                                height: 2px;
                                background-color: $accent1;
                                animation: $animationSpeed 1 slideInFromLeft;
                                border-radius: 1rem;
                                @keyframes slideInFromLeft {
                                    0% {
                                      width: 0px;
                                      opacity: 0;
                                    }
                                    100% {
                                      width: 100%;
                                      opacity: 1;
                                    }
                                  }
                            }
                        }
                    }
                    &.title {
                        font-weight: bold;
                        color: $titleText;
                        margin-bottom: 0.5rem;
                    }
                }
            }
        }
    }
} 
</style>