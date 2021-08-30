<template>
    <section class="sectionCon">

        <!-- header -->
        <header class="sectionHeader">
            <h2>Our Tools Suite</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. aliquam neque.</p>
        </header>

        <!-- suite -->
        <div class="suiteSectBody">
            <!-- Tool list col -->
            <div id="pt_toolsListCol" class="toolsListCol">
                <!-- tool 1 -->
                <section feature class="toolInfoRow active" tabindex="0" role="button" aria-pressed="true">
                    <div class="iconCon">1</div>
                    <div class="textarea">
                        <h3>Playlist Editor</h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus justo, laoreet vestibulum neque quis, dignissim interdum nunc.</p>
                    </div>
                </section>
                <!-- tool 2 -->
                <section feature class="toolInfoRow" tabindex="0" role="button" aria-pressed="false">
                    <div class="iconCon">2</div>
                    <div class="textarea">
                        <h3>Playlist Monitoring</h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus justo, laoreet vestibulum neque quis, dignissim interdum nunc.</p>
                    </div>
                </section>
                <!-- tool 3 -->
                <section feature class="toolInfoRow" tabindex="0" role="button" aria-pressed="false">
                    <div class="iconCon">3</div>
                    <div class="textarea">
                        <h3>Track Release Scheduler</h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus justo, laoreet vestibulum neque quis, dignissim interdum nunc.</p>
                    </div>
                </section>
                <!-- tool 4 -->
                <section feature class="toolInfoRow" tabindex="0" role="button" aria-pressed="false">
                    <div class="iconCon">4</div>
                    <div class="textarea">
                        <h3>Playlist Release Scheduler</h3>
                        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus justo, laoreet vestibulum neque quis, dignissim interdum nunc.</p>
                    </div>
                </section>
                <!-- Mobile arrow nav -->
                <div class="mobArrowCon">
                    <button id="pt_sliderLeftBtn" aria-label="previous feature"></button>
                    <button id="pt_sliderRightBtn" aria-label="next feature"></button>
                </div>
            </div>
            <!-- img col -->
            <div id="pt_slideCon" class="featureImgSlider">
                <div id="pt_sliderCon" class="sliderCon">
                    <div class="imgSlide active">
                        <img loading="lazy" decoding="async" class="desktop" slide src="@/assets/images/featurePhoneSlider1.svg" alt="">
                        <img loading="lazy" decoding="async" class="mobile" slide src="@/assets/images/featurePhoneSlideMobile.svg" alt="">
                    </div>
                    <div class="imgSlide">
                        <img loading="lazy" decoding="async" class="desktop" slide src="@/assets/images/featurePhoneSlider2.svg" alt="">
                        <img loading="lazy" decoding="async" class="mobile" slide src="@/assets/images/featurePhoneSlideMobile.svg" alt="">
                    </div>
                    <div class="imgSlide">
                        <img loading="lazy" decoding="async" class="desktop" slide src="@/assets/images/featurePhoneSlider3.svg" alt="">
                        <img loading="lazy" decoding="async" class="mobile" slide src="@/assets/images/featurePhoneSlideMobile.svg" alt="">
                    </div>
                    <div class="imgSlide">
                        <img loading="lazy" decoding="async" class="desktop" slide src="@/assets/images/featurePhoneSlider4.svg" alt="">
                        <img loading="lazy" decoding="async" class="mobile" slide src="@/assets/images/featurePhoneSlideMobile.svg" alt="">
                    </div>
                </div>
                <div id="pt_sliderPagination" class="paginationCon">
                    <div class="dot active" role="button" aria-pressed="true" index="0" aria-label="first feature"></div>
                    <div class="dot" role="button" aria-pressed="false" index="1" aria-label="second feature"></div>
                    <div class="dot" role="button" aria-pressed="false" index="2" aria-label="third feature"></div>
                    <div class="dot" role="button" aria-pressed="false" index="3" aria-label="fourth feature"></div>
                </div>
            </div>
        </div>

    </section>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    mounted() {
        require('@/assets/js/cardSlider');
    }    
})
</script>

<style lang="scss" scoped>
.suiteSectBody {
    display: flex;
    align-items: stretch;
    @include forBreakpoint(mobile tablet) {
        flex-wrap: wrap-reverse;
    }
    justify-content: space-between;
    gap: 0 40px;
    // Tools list Col
    .toolsListCol { 
        width: 40%;
        min-width: 56rem;
        position: relative;
        @include forBreakpoint(mobile tablet) {
            min-width: auto;
            width: 100%;
        }
        // tools row
        .toolInfoRow {
            width: 100%;
            padding: 2rem;
            background-color: #fff;
            border: 0.1rem solid #fff;
            border-radius: 2rem;
            margin-bottom: 2rem;
            display: flex;
            cursor: pointer;
            transition: 0.3s;
            position: relative;
            &:focus {
                border: 0.1rem solid $accent1;
            }
            &:last-child {
                margin-bottom: 0;
            }
            @include forBreakpoint(mobile tablet) {
                display: none;
                justify-content: center;
                flex-wrap: wrap;
                z-index: 10;
                margin-bottom: 0;
                cursor: default;
                &:focus {
                    border: 0.1rem solid #fff;
                }
            }
            .iconCon {
                background: $gradient;
                height: 4rem;
                width: 4rem;
                min-width: 4rem;
                border-radius: 1rem;
                color: #FFF;
                font-size: 1.6rem;
                font-weight: bold;
                display: flex;
                justify-content: center;
                align-items: center;
                opacity: 0.4;
                @include forBreakpoint(mobile tablet) {
                    height: 6rem;
                    width: 6rem;
                    min-width: 6rem;
                    font-size: 2rem;
                }
            }
            .textarea {
                padding-left: 2rem;
                @include forBreakpoint(mobile tablet) {
                    text-align: center;
                    padding: 2rem 0 0;
                }
                h3 {
                    @include h3;
                    margin-bottom: 1rem;
                }
                p {
                    @include body;
                }
            }
            &.active {
                box-shadow: $shadow;
                .iconCon {
                    opacity: 1;
                }
                @include forBreakpoint(mobile tablet){
                    display: flex;
                }
            }
        }
        // mobile arrow nav
        .mobArrowCon {
            display: none;
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            z-index: 10;
            justify-content: space-between;
            padding: 2rem;
            height: 6rem;
            @include forBreakpoint(mobile tablet) {
                display: flex;
            }
            button {
                background-color: #F8F8F8;
                border: 0.1rem solid #F4F4F4;
                border-radius: 50%;
                height: 4rem;
                width: 4rem;
                transition: $animationSpeed;
                display: flex;
                justify-content: center;
                align-items: center;
                &:hover {
                    background-color: #E8E8E8;
                }
                &:after {
                    content: '';
                    background-image: url('@/assets/images/icons/chevron-right.svg');
                    background-repeat: no-repeat;
                    background-size: contain;
                    background-position: center;
                    height: 2rem;
                    width: 2rem;
                    display: block;
                }
                &:first-child {
                    &:after {
                        transform: rotate(180deg);
                    }
                }
            }
        }
    }
    // Img col
    .featureImgSlider {
        width: 60%;
        min-height: 100%;
        @include gradientAnimation;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 2rem;
        overflow: hidden;
        position: relative;
        @include forBreakpoint(mobile tablet) {
            width: 100%;
            min-height: auto;
            margin-bottom: -20px;
            padding: 0 0 4rem;
        }
        .sliderCon {
                display: flex;
                align-items: center;
                width: 80%;
                transition: 0.3s;
                @include forBreakpoint(mobile tablet) {
                    height: 50rem;
                }
                .imgSlide {
                    min-width: 80%;
                    padding: 0 2rem;
                    transition: 0.3s;
                    .mobile {
                        display: none;
                    }
                    @include forBreakpoint(mobile tablet) {
                        height: 100%;
                        display: flex;
                        align-items: center;
                        .desktop {
                            display: none;
                        }
                        .mobile {
                            display: flex;
                        }
                        img {
                            height: calc(100% - 8rem);
                            object-fit: contain;
                        }
                    }
                    &.active {
                        min-width: 100%;
                    }
                    img {
                        width: 100%;
                    }
                }
        }
        .paginationCon {
            display: flex;
            gap: 0 1rem;
            justify-content: center;
            position: absolute;
            left: 0;
            right: 0;
            bottom: 3rem;
            @include forBreakpoint(mobile tablet) {
                bottom: 4rem;
            }
            .dot {
                height: 1.5rem;
                width: 1.5rem;
                border-radius: 50%;
                border: 0.2rem solid #fff;
                cursor: pointer;
                transition: $animationSpeed;
                &:hover {
                    background-color: #fff;
                }
                &.active {
                    background-color: #fff;
                }
            }
        }
    }
}
</style>