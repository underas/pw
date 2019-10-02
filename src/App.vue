<template>
  <v-app>
    <transition name="fade">
      <v-app-bar
          app
          dark
          class="bar__transition"
          color="#ffb869"
          v-if="showNav"
      >

        <div class="flex-grow-1"></div>

        <v-app-bar-nav-icon color="#dadad" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      </v-app-bar>
    </transition>
    <v-navigation-drawer
        app
        temporary
        v-model="drawer"
        right
        width="260px"
    >

      <v-list dense>

        <v-list-item
            v-for="item in items"
            :key="item.title"
            link

        >
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-content class="contentBlock">
      <div class="mask">
        <svg id="logo" width="899" height="158" viewBox="0 0 899 158" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path
              d="M60.536 117L26.552 72.36V117H1.92801V15.912H26.552V60.264L60.248 15.912H89.192L50.024 65.448L90.632 117H60.536Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M178.078 75.528C178.078 77.832 177.934 80.232 177.646 82.728H121.918C122.302 87.72 123.886 91.56 126.67 94.248C129.55 96.84 133.054 98.136 137.182 98.136C143.326 98.136 147.598 95.544 149.998 90.36H176.206C174.862 95.64 172.414 100.392 168.862 104.616C165.406 108.84 161.038 112.152 155.758 114.552C150.478 116.952 144.574 118.152 138.046 118.152C130.174 118.152 123.166 116.472 117.022 113.112C110.878 109.752 106.078 104.952 102.622 98.712C99.1663 92.472 97.4383 85.176 97.4383 76.824C97.4383 68.472 99.1183 61.176 102.478 54.936C105.934 48.696 110.734 43.896 116.878 40.536C123.022 37.176 130.078 35.496 138.046 35.496C145.822 35.496 152.734 37.128 158.782 40.392C164.83 43.656 169.534 48.312 172.894 54.36C176.35 60.408 178.078 67.464 178.078 75.528ZM152.878 69.048C152.878 64.824 151.438 61.464 148.558 58.968C145.678 56.472 142.078 55.224 137.758 55.224C133.63 55.224 130.126 56.424 127.246 58.824C124.462 61.224 122.734 64.632 122.062 69.048H152.878Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path d="M227.213 93.96L244.637 36.648H270.845L242.333 117H211.949L183.437 36.648H209.789L227.213 93.96Z"
                stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M293.593 28.296C289.273 28.296 285.721 27.048 282.937 24.552C280.249 21.96 278.905 18.792 278.905 15.048C278.905 11.208 280.249 8.04001 282.937 5.54401C285.721 2.95201 289.273 1.65601 293.593 1.65601C297.817 1.65601 301.273 2.95201 303.961 5.54401C306.745 8.04001 308.137 11.208 308.137 15.048C308.137 18.792 306.745 21.96 303.961 24.552C301.273 27.048 297.817 28.296 293.593 28.296ZM305.833 36.648V117H281.209V36.648H305.833Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M372.638 35.784C382.046 35.784 389.534 38.856 395.102 45C400.766 51.048 403.598 59.4 403.598 70.056V117H379.118V73.368C379.118 67.992 377.726 63.816 374.942 60.84C372.158 57.864 368.414 56.376 363.71 56.376C359.006 56.376 355.262 57.864 352.478 60.84C349.694 63.816 348.302 67.992 348.302 73.368V117H323.678V36.648H348.302V47.304C350.798 43.752 354.158 40.968 358.382 38.952C362.606 36.84 367.358 35.784 372.638 35.784Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path d="M508.261 15.912V117H483.637V75.384H445.333V117H420.709V15.912H445.333V55.512H483.637V15.912H508.261Z"
                stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M605.381 36.648V117H580.757V106.056C578.261 109.608 574.853 112.488 570.533 114.696C566.309 116.808 561.605 117.864 556.421 117.864C550.277 117.864 544.853 116.52 540.149 113.832C535.445 111.048 531.797 107.064 529.205 101.88C526.613 96.696 525.317 90.6 525.317 83.592V36.648H549.797V80.28C549.797 85.656 551.189 89.832 553.973 92.808C556.757 95.784 560.501 97.272 565.205 97.272C570.005 97.272 573.797 95.784 576.581 92.808C579.365 89.832 580.757 85.656 580.757 80.28V36.648H605.381Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M618.173 76.68C618.173 68.424 619.709 61.176 622.781 54.936C625.949 48.696 630.221 43.896 635.597 40.536C640.973 37.176 646.973 35.496 653.597 35.496C659.261 35.496 664.205 36.648 668.429 38.952C672.749 41.256 676.061 44.28 678.365 48.024V36.648H702.989V117H678.365V105.624C675.965 109.368 672.605 112.392 668.285 114.696C664.061 117 659.117 118.152 653.453 118.152C646.925 118.152 640.973 116.472 635.597 113.112C630.221 109.656 625.949 104.808 622.781 98.568C619.709 92.232 618.173 84.936 618.173 76.68ZM678.365 76.824C678.365 70.68 676.637 65.832 673.181 62.28C669.821 58.728 665.693 56.952 660.797 56.952C655.901 56.952 651.725 58.728 648.269 62.28C644.909 65.736 643.229 70.536 643.229 76.68C643.229 82.824 644.909 87.72 648.269 91.368C651.725 94.92 655.901 96.696 660.797 96.696C665.693 96.696 669.821 94.92 673.181 91.368C676.637 87.816 678.365 82.968 678.365 76.824Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M769.763 35.784C779.171 35.784 786.659 38.856 792.227 45C797.891 51.048 800.723 59.4 800.723 70.056V117H776.243V73.368C776.243 67.992 774.851 63.816 772.067 60.84C769.283 57.864 765.539 56.376 760.835 56.376C756.131 56.376 752.387 57.864 749.603 60.84C746.819 63.816 745.427 67.992 745.427 73.368V117H720.803V36.648H745.427V47.304C747.923 43.752 751.283 40.968 755.507 38.952C759.731 36.84 764.483 35.784 769.763 35.784Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
          <path
              d="M848.362 35.496C854.026 35.496 858.97 36.648 863.194 38.952C867.514 41.256 870.826 44.28 873.13 48.024V36.648H897.754V116.856C897.754 124.248 896.266 130.92 893.29 136.872C890.41 142.92 885.946 147.72 879.898 151.272C873.946 154.824 866.506 156.6 857.578 156.6C845.674 156.6 836.026 153.768 828.634 148.104C821.242 142.536 817.018 134.952 815.962 125.352H840.298C841.066 128.424 842.89 130.824 845.77 132.552C848.65 134.376 852.202 135.288 856.426 135.288C861.514 135.288 865.546 133.8 868.522 130.824C871.594 127.944 873.13 123.288 873.13 116.856V105.48C870.73 109.224 867.418 112.296 863.194 114.696C858.97 117 854.026 118.152 848.362 118.152C841.738 118.152 835.738 116.472 830.362 113.112C824.986 109.656 820.714 104.808 817.546 98.568C814.474 92.232 812.938 84.936 812.938 76.68C812.938 68.424 814.474 61.176 817.546 54.936C820.714 48.696 824.986 43.896 830.362 40.536C835.738 37.176 841.738 35.496 848.362 35.496ZM873.13 76.824C873.13 70.68 871.402 65.832 867.946 62.28C864.586 58.728 860.458 56.952 855.562 56.952C850.666 56.952 846.49 58.728 843.034 62.28C839.674 65.736 837.994 70.536 837.994 76.68C837.994 82.824 839.674 87.72 843.034 91.368C846.49 94.92 850.666 96.696 855.562 96.696C860.458 96.696 864.586 94.92 867.946 91.368C871.402 87.816 873.13 82.968 873.13 76.824Z"
              stroke="white" stroke-width="2" mask="url(#path-1-outside-1)"/>
        </svg>

      </div>
      <v-img :src="bannerBG" :aspect-ratio="4/3" cover class="banner"></v-img>
      <v-container>
        <div class="about">
          <div class="row">
            <v-col cols="12"><h2>關於我</h2></v-col>
          </div>
        </div>
        <v-row>

          <v-col cols="12" md="6">12</v-col>
        </v-row>
      </v-container>x
    </v-content>
  </v-app>
</template>

<script>

    export default {
        name: 'App',
        components: {},
        data: () => ({
            drawer: false,
            showNav: false,
            bannerBG: require('@/assets/image/bg.jpg'),
            items: [
                {title: 'Home', icon: 'mdi-home'},
                {title: 'About', icon: 'mdi-question_answer'},
            ],
        }),
        mounted() {
            window.addEventListener('scroll', this.handle);

            if (window.pageYOffset > 100) {
                this.showNav = true;
            } else {
                this.showNav = false;
            }
        },
        methods: {
            handle() {
                if (window.pageYOffset > 100) {
                    this.showNav = true;
                } else {
                    this.showNav = false;
                }
            }
        }
    };
</script>

<style lang="scss" >

  .bar__transition {
    transition: 0.5s;
  }

  .contentBlock {
    padding-top: 0 !important;
    position: relative;

    .mask {
      position: absolute;
      top: 0;
      left: 0;
      background-color: rgba(0, 0, 0, 0.6);
      z-index: 1;
      width: 100%;
      height: 100vh;
      transition: .5s;
      animation: hideAndShow 3s ease-in-out infinite;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 0 10px;

      #logo {
        animation: fill 0.5s ease forwards 4.5s;
      }

      #logo path:nth-child(1) {
        stroke-dasharray: 538;
        stroke-dashoffset: 538;
        animation: line-anim 2s ease forwards 1s;
      }

      #logo path:nth-child(2) {
        stroke-dasharray: 451;
        stroke-dashoffset: 451;
        animation: line-anim 2s ease forwards 1.8s;
      }

      #logo path:nth-child(3) {
        stroke-dasharray: 373;
        stroke-dashoffset: 373;
        animation: line-anim 2s ease forwards 2s;

      }

      #logo path:nth-child(4) {
        stroke-dasharray: 298;
        stroke-dashoffset: 298;
        animation: line-anim 2s ease forwards 2.1s;

      }

      #logo path:nth-child(5) {
        stroke-dasharray: 431;
        stroke-dashoffset: 431;
        animation: line-anim 2s ease forwards 2.2s;

      }

      #logo path:nth-child(6) {
        stroke-dasharray: 539;
        stroke-dashoffset: 539;
        animation: line-anim 2s ease forwards 2.3s;

      }

      #logo path:nth-child(7) {
        stroke-dasharray: 431;
        stroke-dashoffset: 431;
        animation: line-anim 2s ease forwards 2.4s;

      }

      #logo path:nth-child(8) {
        stroke-dasharray: 451;
        stroke-dashoffset: 451;
        animation: line-anim 2s ease forwards 2.5s;

      }

      #logo path:nth-child(9) {
        stroke-dasharray: 431;
        stroke-dashoffset: 431;
        animation: line-anim 1.7s ease forwards 2.6s;

      }

      #logo path:nth-child(10) {
        stroke-dasharray: 621;
        stroke-dashoffset: 621;
        animation: line-anim 2s ease forwards 2.7s;

      }
    }

    .banner {
      height: 100vh;
      /*filter: grayscale(100%);*/
    }

    .about {
      min-height: 100vh;

      h2{

      }
    }
  }

  //animation

  .fade-enter-active, .fade-leave-active {
    transition: opacity 1s;
  }

  .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */
  {
    opacity: 0;
  }


  @keyframes hideAndShow {
    0% {
      background-color: rgba(0, 0, 0, 0.3);
    }
    50% {
      background-color: rgba(0, 0, 0, 0.7);
    }
    100% {
      background-color: rgba(0, 0, 0, 0.3);
    }
  }

  @keyframes line-anim {
    to {
      stroke-dashoffset: 0;
    }
  }

  @keyframes fill {
    from {
      fill: transparent;
    }
    to {
      fill: white;
    }
  }


</style>
