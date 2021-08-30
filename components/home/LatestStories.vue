<template>
    <section class="sectionCon">

        <!-- header -->
        <header class="sectionHeader">
            <h2>Checkout Our Latest Stories</h2>
            <p>Have a read of our recent stories and news, and if you would like - sign up to our newsletter to stay informed with playlist tools.</p>
            <div class="newsletterInpCon">
                <input class="inpStyle" type="text" placeholder="Enter your email address">
                <button aria-label="submit email"></button>
            </div>
        </header>

        <!-- blog posts -->
        <section class="storySectBody">
            
            <!-- Blog 1 -->
            <nuxt-link class="blogCol" to="https://mozilla.org">
                <!-- Bg image -->
                <picture>
                    <source srcset="@/assets/images/blog/blog1/main.avif" type="image/avif">
                    <source srcset="@/assets/images/blog/blog1/main.webp" type="image/webp">
                    <img class="blogBgImg" loading="lazy" decoding="async" src="@/assets/images/blog/blog1/main.jpeg" alt="Musician singing on stage">
                </picture>
                <!-- Textarea -->
                <div class="blogPreview">
                    <div class="categoryRow">
                        <div class="category">news</div>
                    </div>
                    <h3>Future Features For PlaylistTools.io</h3>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus.</p>
                </div>
            </nuxt-link>

            <!-- Blog 2 -->
            <nuxt-link class="blogCol" to="https://mozilla.org">
                <!-- Bg image -->
                <picture>
                    <source srcset="@/assets/images/blog/blog2/main.avif" type="image/avif">
                    <source srcset="@/assets/images/blog/blog2/main.webp" type="image/webp">
                    <img class="blogBgImg" loading="lazy" decoding="async" src="@/assets/images/blog/blog2/main.jpeg" alt="Music editing software">
                </picture>
                <!-- Textarea -->
                <div class="blogPreview">
                    <div class="categoryRow">
                        <div class="category">news</div>
                    </div>
                    <h3>Future Features For PlaylistTools.io</h3>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus.</p>
                </div>
            </nuxt-link>

        </section>

    </section>
</template>

<style lang="scss" scoped>
// Header input
.newsletterInpCon {
    width: 80%;
    margin: 2rem auto 0;
    box-shadow: $shadow;
    border-radius: 3rem;
    position: relative;
    @include forBreakpoint(mobile) {
        width: 90%;
    }
    .inpStyle {
        @include inpStyle;
        height: 6rem;
        border-radius: 3rem;
        padding-right: 6rem;
    }
    button {
        position: absolute;
        top: 0.2rem;
        right:  0.3rem;
        bottom:  0.2rem;
        width: 5.7rem;
        height: 5.7rem;
        border-radius: 0 3rem 3rem 0;
        background-color: #fff;
        cursor: pointer;
        border: none;
        &::before {
            content: '';
            display: block;
            margin: 0 auto;
            border-radius: 50%;
            transition: $animationSpeed;
            background-color: $accent1;
            height: 4rem;
            width: 4rem;
        }
        &:hover {
            &::before {
                background-color: $accent1Dark;
            }   
        }
        &:focus {
            &::before {
                background-color: $accent1Dark;
                transform: scale(1.1);
            }    
        }
    }
}
// Story body
.storySectBody {
    width: 100%;
    display: flex;
    gap: 0 2rem;
    @include forBreakpoint(mobile) {
        flex-wrap: wrap;
    }
    .blogCol {
        width: 50%;
        position: relative;
        overflow: hidden;
        border-radius: 2rem;
        cursor: pointer;
        border: 0.1rem solid transparent;
        text-decoration: none;
        @include forBreakpoint(mobile) {
            width: 100%;
            &:first-child {
                margin-bottom: 2rem;
            }
        }
        &:focus {
            .blogBgImg {
                transform: scale(1.1);
            } 
            border: 0.1rem solid $accent1;
        }
        &:hover {
            .blogBgImg {
                transform: scale(1.1);
            }
            border: 0.1rem solid $accent1;
        }
        // bg img
        .blogBgImg {
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            object-fit: cover;
            object-position: center;
            z-index: 0;
            transition: $animationSpeed;
            border-radius: 2rem;
        }
        // textarea
        .blogPreview {
            height: 42rem;
            background: linear-gradient(180deg, rgba(0,0,0,0.1), rgba(0,0,0,0.5));
            position: relative;
            z-index: 10;
            display: flex;
            flex-direction: column;
            justify-content: flex-end;
            padding: 2rem;
            .categoryRow {
                width: 100%;
                display: flex;
                margin-bottom: 2rem;
                .category {
                    background-color: $accent1;
                    color: #fff;
                    border-radius: 20px;
                    padding: 0.5rem 1rem;
                    font-size: 1.4rem;
                }
            }
            h3 {
                @include h3;
                color: #fff;
                max-width: 40rem;
            }
            p {
                @include body;
                color: #E0E0E0;
                margin-top: 1rem;
                max-width: 40rem;
            }
        }
    }
}

</style>