<template>
    <section class="sectionCon">

        <!-- header -->
        <header class="sectionHeader">
            <h2>Our Pricing</h2>
            <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. aliquam neque.</p>
        </header>

        <!-- pricing tables -->
        <div class="pricingSectBody">
            
            <div class="privingTableCon">
                <!-- Table 1 -->
                <section class="pricingTableCol">
                    <div class="pricingInner">
                        <p class="packageNameP">Free</p>
                        <h3>£0 <span>/month</span></h3>
                        <p class="packageDesc">For those that have a couple of playlists they want to manage.</p>
                        <ul class="packageFeatures">
                            <li>10 Actions <span>/month</span></li>
                            <li>Monitor 2 Playlists</li>
                            <li>Schedule 5 Track Releases</li>
                            <li>Schedule 2 Playlist Releases</li>
                        </ul>
                        <nuxt-link to="https://app.playlisttools.io/settings">choose plan</nuxt-link>
                    </div>
                </section>

                <!-- Table 2 -->
                <section class="pricingTableCol active">
                    <div class="pricingInner">
                        <p class="packageNameP">Premium</p>
                        <h3>£5.99 <span>/month</span></h3>
                        <p class="packageDesc">For those small business, or independent curators.</p>
                        <ul class="packageFeatures">
                            <li>Unlimited Actions</li>
                            <li>Monitor 20 Playlists</li>
                            <li>Schedule 40 Track Releases</li>
                            <li>Schedule 20 Playlist Releases</li>
                        </ul>
                        <nuxt-link to="https://app.playlisttools.io/settings">choose plan</nuxt-link>
                    </div>
                </section>

                <!-- Table 3 -->
                <section class="pricingTableCol">
                    <div class="pricingInner">
                        <p class="packageNameP">Business</p>
                        <h3>£99.99 <span>/month</span></h3>
                        <p class="packageDesc">For those large businesses with hundreds of playlists.</p>
                        <ul class="packageFeatures">
                            <li>Unlimited Actions</li>
                            <li>Monitor Unlimited Playlists</li>
                            <li>Schedule Unlimited Track Releases</li>
                            <li>Schedule Unlimited Playlist Releases</li>
                        </ul>
                        <nuxt-link to="https://app.playlisttools.io/settings">choose plan</nuxt-link>
                    </div>
                </section>
            </div>

        </div>

    </section>
</template>

<style lang="scss" scoped>
.pricingSectBody {


    .privingTableCon {
        width: 90%;
        margin: 0 auto;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(28rem, 1fr));
        gap: 2rem;
        align-items: center;
        // Pricing col
        .pricingTableCol {
            background-color: #fff;
            border-radius: 2rem;
            box-shadow: $shadow;
            position: relative;
            &.active {
                .pricingInner  {
                    padding: 4rem 2rem;
                }
                &::before {
                    content: '';
                    @include gradientAnimation;
                    position: absolute;
                    left: -0.2rem;
                    top: -0.2rem;
                    bottom: -0.2rem;
                    right: -0.2rem;
                    z-index: 0;
                    border-radius: 2rem;
                }
            }
            .pricingInner {
                z-index: 10;
                position: relative;
                background-color: #fff;
                border-radius: 1.8rem;
                height: 100%;
                width: 100%;
                padding: 2rem;
                .packageNameP {
                    font-size: 1.8rem;
                    color: $titleText;
                    margin-bottom: 1rem;
                    font-weight: bold;
                } 
                h3 {
                    @include h3;
                    font-size: 2.4rem;
                    span {
                        font-size: 1.6rem;
                        color: rgb(148, 148, 148)
                    }
                }
                .packageDesc {
                    font-size: 1.6rem;
                    color: #707070;
                    max-width: 25rem;
                    margin-top: 0.5rem;
                } 
                .packageFeatures {
                    margin: 2.5rem 0;
                    li {
                        font-size: 1.6rem;
                        color: rgb(22, 22, 22);
                        display: flex;
                        padding: 0.5rem 0;
                        &::before {
                            display: block;
                            content: '';
                            height: 2rem;
                            width: 2rem;
                            margin-right: 1rem;
                            border-radius: 50%;
                            background-color: rgb(180, 180, 180);
                        }
                    }
                } 
                a {
                    @include defaultBtnStyle;
                    width: 100%;
                    display: block;
                    background-color: $accent1;
                    position: relative;
                    &::before {
                        @include gradientAnimation;
                        content: 'choose plan';
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
                        transform: scale(1.07);
                    }
                }
            }

        }
    }
}
</style>