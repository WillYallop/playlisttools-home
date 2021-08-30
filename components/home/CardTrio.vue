<template>
    <section class="sectionCon">
        <!-- header -->
        <header class="sectionHeader">
            <h2>Why Use Playlist Tools?</h2>
            <p>Not only do we have a wide tool set, to help you manage, monitor and create playlists, but we are also incredibly flexible.</p>
        </header>
        <!-- points contianer -->
        <div class="pointsCon">
            <!-- col -->
            <section class="col">
                <div class="iconCon"><img src="@/assets/images/icons/music-solid.svg" loading="lazy" decoding="async" alt="Music note icon" width="60px" height="60px"></div>
                <h3>Link all your Spotify accounts!</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus.</p>
            </section>
            <!-- col -->
            <section class="col">
                <div class="iconCon"><img src="@/assets/images/icons/music-solid.svg" loading="lazy" decoding="async" alt="Music note icon" width="60px" height="60px"></div>
                <h3>No cost for casual users!</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus.</p>
            </section>
            <!-- col -->
            <section class="col">
                <div class="iconCon"><img src="@/assets/images/icons/music-solid.svg" loading="lazy" decoding="async" alt="Music note icon" width="60px" height="60px"></div>
                <h3>Works on every platform!</h3>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Maecenas quis aliquam neque. Pellentesque tellus.</p>
            </section>
        </div>
    </section>
</template>

<style lang="scss" scoped>
.pointsCon {
    width: 100%;
    display: flex;
    gap: 2rem;
    align-items: center;
    margin-bottom: 2rem;
    @media only screen and (max-width: 1024px) {
        flex-wrap: wrap;
    }
    .col {
        width: 33.33%;
        background-color: $background;
        border-radius: 2rem;
        box-shadow: $shadow;
        padding: 2rem;
        @media only screen and (max-width: 1024px) {
            width: 90%;
            &:nth-child(2) {
                margin-left: 10%;
            }
        }
        .iconCon {
            width: 4rem;
            margin-bottom: 2rem;
            img {
                width: 4rem;
                height: 4rem;
            }
        }
        h3 {
            @include h3;
            margin-bottom: 1rem;
        }
        p {
            @include body;
        }
    }
}
</style>