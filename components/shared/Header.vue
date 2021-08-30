<template>
    <header id="pt_headerComp" class="headerCon">
        <div class="wrapper">
            <nuxt-link to="/" aria-label="Go to the home page" class="logoImg"><img class="logoImg" src="@/assets/images/logo.svg" alt="PlaylistTools.io"></nuxt-link>
            <nav class="navCon">
                <nuxt-link class="navLink" to="/blogs" aria-label="Go to the blog page">blogs</nuxt-link>
                <button v-on:click="handleNavDropdown" class="navLink toggleBtn" :aria-expanded="dropdownVisibile ? 'true' : 'false'" aria-label="Open tools navigation dropdown">
                    <span class="desktopInner">
                        tools 
                        <img src="@/assets/images/icons/chevron-circle-down-solid.svg" loading="lazy" decoding="async" alt="Dropdown icon">
                    </span>
                    <span class="mobileInner">
                        <img src="@/assets/images/icons/bars-solid.svg" loading="lazy" decoding="async" alt="Toggle navigation button">
                    </span>
                </button>
                <nuxt-link class="navSignUpLink" to="#" aria-label="Sign up to PlaylistTools.io!">sign up</nuxt-link>
            </nav>
        </div>
        <!-- Dropdown -->
        <nav class="toolDropdownRow" :class="{ 'closed' : !dropdownVisibile }" :style="{ 'maxHeight' : `${dropdownMaxHeight}px` }" role="navigation">
            <div id="pt_toolDropdownRowWrapper" ref="toolDropdownRowWrapper" class="wrapper">
                <!-- Mobile Links -->
                <ul class="mobileLinks">
                    <li><nuxt-link to="/" :tabindex="navTabIndex" aria-label="Go to the home page">home <img src="@/assets/images/icons/chevron-circle-down-solid.svg" loading="lazy" decoding="async" alt="Dropdown icon"></nuxt-link></li>
                    <li><nuxt-link to="/blogs" :tabindex="navTabIndex" aria-label="Go to the blog page">blog <img src="@/assets/images/icons/chevron-circle-down-solid.svg" loading="lazy" decoding="async" alt="Dropdown icon"></nuxt-link></li>
                </ul>
                <!-- Links -->
                <ul class="dropdownMenu">
                    <li class="menuItem">
                        <nuxt-link to="#" aria-label="Reorganise your playlists automatically!" :tabindex="navTabIndex">
                            <div class="icon"></div>
                            <ul>
                                <li class="title">shuffle playlist</li>
                                <li class="desc">Re-order your playlist how you like with a selection of presets.</li>
                            </ul>
                        </nuxt-link>
                    </li>
                    <li class="menuItem">
                        <nuxt-link to="#" aria-label="Remove duplicates and unplayable tracks from your playlists." :tabindex="navTabIndex">
                            <div class="icon"></div>
                            <ul>
                                <li class="title">remove duplicates</li>
                                <li class="desc">Automatically remove duplicate and unplayable tracks from your playlist.</li>
                            </ul>
                        </nuxt-link>
                    </li>
                    <li class="menuItem">
                        <nuxt-link to="#" aria-label="Generate brand new Spotify playlists." :tabindex="navTabIndex">
                            <div class="icon"></div>
                            <ul>
                                <li class="title">generate playlist</li>
                                <li class="desc">Create brand new playlists based on selected tracks, genres or artists.</li>
                            </ul>  
                        </nuxt-link>
                    </li>
                    <li class="menuItem">
                        <nuxt-link to="/playlist-cover-maker" aria-label="Make unique playlist cover art with our templates!" :tabindex="navTabIndex">
                            <div class="icon"></div>
                            <ul>
                                <li class="title">playlist cover maker</li>
                                <li class="desc">Create unique, custom cover art for your playlist with our templates.</li>
                            </ul>
                        </nuxt-link>
                    </li>
                </ul>
                <!-- cta -->
                <div class="ctaRow">
                    <div class="textArea">
                        <h2 class="title">Get access to our full suite of tools!</h2>
                        <p class="body">Creating an account and linking your SPotify takes less than a minute. So what are you waiting for. Sign up now!</p>
                    </div>
                    <div class="btnCol">
                        <nuxt-link to="#" aria-label="Sign up to PlaylistTools.io!" :tabindex="navTabIndex">sign up</nuxt-link>
                        <nuxt-link to="#" aria-label="Sign in to PlaylistTools.io!" :tabindex="navTabIndex">sign in</nuxt-link>
                    </div>
                </div>
                <!-- Mobile Btn -->
                <nuxt-link class="mobileBtnSignUp" to="#" aria-label="Sign up to PlaylistTools.io!" :tabindex="navTabIndex">sign up</nuxt-link>
            </div>
        </nav>
    </header>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    data() {
        return {
            dropdownMaxHeight: 0,
            navTabIndex: -1,
            dropdownVisibile: false,
        }
    },
    mounted(): void  {
        this.$nextTick(() => {
            this.onResize();
        });
        window.addEventListener('resize', this.onResize);
    },
    methods: {
        handleNavDropdown(): void {
            this.dropdownVisibile = !this.dropdownVisibile;
            if(this.dropdownVisibile) this.dropdownMaxHeight = (this.$refs["toolDropdownRowWrapper"] as HTMLElement).offsetHeight, this.navTabIndex = 0;
            else this.dropdownMaxHeight = 0, this.navTabIndex = -1;
        },
        onResize(): void {
            if(this.dropdownMaxHeight) {
                this.dropdownMaxHeight = (this.$refs["toolDropdownRowWrapper"] as HTMLElement).offsetHeight, this.navTabIndex = 0;
            }
        }
    },
    destroyed() {
        console.log('destroyed');
        window.removeEventListener('resize', this.onResize);
    }
})
</script>

<style lang="scss" scoped>
.headerCon {
    position: fixed;
    top: 2rem;
    left: 2rem;
    right: 2rem;
    min-height: 8rem;
    background-color: $background;
    border-radius: 2rem;
    box-shadow: $shadow;
    transition: none;
    overflow: hidden;
    z-index: 1000;
    .wrapper {
        @include wrapper;
        height: 8rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding-top: 2rem;
        padding-bottom: 2rem;
        border-bottom: 0.1rem solid lighten($accent1, 40%);
        .logoImg {
            height: 36px;
            transition: transform $animationSpeed;
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
        .navCon {
            height: 6rem;
            display: flex;
            align-items: center;
            .navLink {
                @include title;
                margin-right: 4rem;
                text-decoration: none;
                padding: 1rem;
                background-color: transparent;
                border: none;
                position: relative;
                cursor: pointer;
                &:last-child {
                    margin-right: 0;
                }
                &:focus, &:hover {
                    &::after {
                        content: '';
                        position: absolute;
                        left: 0;
                        bottom: -4px;
                        width: 100%;
                        height: 4px;
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
                img {
                    height: 1rem;
                    width: 1rem;
                    margin-left: 0.5rem;
                }
                @media only screen and (max-width: 90rem) {
                    display: none;
                }
                &.toggleBtn {
                    .mobileInner {
                        display: none;
                        img {
                            height: 25px;
                            width: 28.56px;
                        }
                    }
                    @media only screen and (max-width: 90rem) {
                        display: flex;
                        margin-right: 0;
                        .mobileInner {
                            display: flex;
                        }
                        .desktopInner {
                            display: none;
                        }
                        &:focus, &:hover {
                            transform: scale(1.1);
                            &::after {
                                display: none;
                            }
                        }
                    }
                }
            }
            .navSignUpLink {
                @include defaultBtnStyle;
                background-color: $accent1;
                position: relative;
                &::before {
                    @include gradientAnimation;
                    content: 'sign up';
                    opacity: 0;
                    position: absolute;
                    top: 0;
                    left: 0;
                    right: 0;
                    bottom: 0;
                    border-radius: 2rem;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    transition: $animationSpeed;
                }
                &:hover {
                    &::before  {
                        opacity: 1;
                    }
                }
                &:focus {
                    transform: scale(1.1);
                }
                @media only screen and (max-width: 90rem) {
                    display: none;
                }
            }
        }
    }
    // Dropdown
    .toolDropdownRow {
        background-color: $background;
        transition: max-height $animationSpeed ease-out;
        // display: block;
        height: auto;
        max-height: 20rem;
        &.closed {
            // display: none;
            max-height: 0;
        }
        .wrapper {
            @include wrapper;
            height: auto;
            padding-bottom: 2rem;
            display: flex;
            flex-wrap: wrap;
            max-height: calc(100vh - 22rem);
            overflow-y: scroll;
            &::-webkit-scrollbar {
                display: none;
            }
            // Mobile btns
            .mobileLinks {
                display: none;
                width: 100%;
                margin-top: 2rem;
                @media only screen and (max-width: 90rem) {
                    display: block;
                }
                li {
                    width: 100%;
                    margin-bottom: 1rem;
                    &:last-child {
                        margin-bottom: 0;
                    }
                    a {
                        @include title;
                        display: flex;
                        justify-content: space-between;
                        align-items: center;
                        width: 100%;
                        text-decoration: none;
                        padding: $padding;
                        border-radius: 2rem;
                        border: 0.1rem solid lighten($accent1, 40%);
                        
                        &:hover {
                            background-color: lighten($accent1, 40%);
                            border: 0.1rem solid lighten($accent1, 35%);
                        }
                        &:focus {
                            background-color: lighten($accent1, 40%);
                            border: 0.1rem solid lighten($accent1, 35%);
                        }
                        img {
                            height: 1.5rem;
                            width: 1.5rem;
                            transform: rotate(270deg)
                        }
                    }
                }
            }
            .mobileBtnSignUp {
                @include defaultBtnStyle;
                width: 100%;
                background-color: $accent1;
                display: none;
                @media only screen and (max-width: 90rem) {
                    display: block;
                }
                &:focus, &:hover {
                    background-color: $accent1Dark;
                }
            }
            // Menu
            .dropdownMenu {
                width: 100%;
                display: grid;
                gap: 1rem;
                padding-top: 2rem;
                grid-template-columns: repeat(auto-fit, minmax(26rem, 1fr));
                margin-bottom: 2rem;
                .menuItem {
                    a {
                        display: flex;
                        text-decoration: none;
                        padding: $padding;
                        border-radius: 2rem;
                        border: 0.1rem solid lighten($accent1, 40%);
                        &:hover {
                            background-color: lighten($accent1, 40%);
                            border: 0.1rem solid lighten($accent1, 35%);
                        }
                        &:focus {
                            background-color: lighten($accent1, 40%);
                            border: 0.1rem solid lighten($accent1, 35%);
                        }
                        .icon {
                            width: 4rem;
                            height: 4rem;
                            min-width: 4rem;
                            border-radius: 50%;
                            background-color: lighten($accent1, 35%);
                        }
                        ul {
                            padding-left: 2rem;
                            .title {
                                @include title;
                                margin-bottom: 1rem;
                            }
                            .desc {
                                @include body;
                            }
                        }
                    }
                }
            }
            // cta
            .ctaRow {
                @include gradientAnimation;
                width: 100%;
                padding: $padding;
                display: flex;
                flex-wrap: wrap;
                justify-content: space-between;
                border-radius: 2rem;
                .textArea {
                    .title {
                        @include title;
                        color: $titleLight;
                        font-size: 1.8rem;
                        margin-bottom: 1rem;
                    }
                    .body {
                        color: $bodyLight;
                        font-size: 1.6rem;
                        max-width: 40rem;
                    }
                }
                .btnCol {
                    display: flex;
                    flex-wrap: wrap;
                    align-items: center;
                    gap: 1rem;
                    a { 
                        @include defaultBtnStyle;
                        display: block;
                        border: 0.2rem solid #fff;
                        &:first-child {
                            margin-right: 1rem;
                        }
                        &:hover {
                            background-color: #fff;
                            color: $titleText;
                        }
                        &:focus {
                            background-color: #fff;
                            color: $titleText;
                        }
                    }
                }
                @media only screen and (max-width: 90rem) {
                    display: none;
                }
            }
        }

    }
}
</style>