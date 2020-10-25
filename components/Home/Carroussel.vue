<template>
  <div class="carroussel">
    <font-awesome-icon
      :icon="['fas', 'chevron-left']"
      class="carroussel__chevron-left"
      v-on:click="switchImageLeft"
    />
    <div class="carroussel__images">
      <div
        v-for="img in images"
        :key="img.text"
        v-bind:class="{ selected : img.selected , switchImagesLeft : img.switchLeftAnimation ,
         switchImagesRigth : img.switchRigtAnimation, switchImagesFromRigth: img.switchImagesFromRigth,
          switchImagesFromLeft: img.switchImagesFromLeft,}"
        class="carroussel__img"
      >
        <img v-bind:src="img.path" alt="The images was not found" />
        <div class="img__text">{{ img.text }}</div>
      </div>
    </div>
    <font-awesome-icon
      :icon="['fas', 'chevron-right']"
      class="carroussel__chevron-right"
      v-on:click="switchImageRight"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        {
          path: "/home-office.png",
          text: "Hello",
          selected: true,
          switchLeftAnimation: false,
          switchRigtAnimation: false,
          switchImagesFromRigth: false,
          switchImagesFromLeft: false,
        },
        {
          path: "/home-office.png",
          text: "Promo",
          selected: false,
          switchLeftAnimation: false,
          switchRigtAnimation: false,
          switchImagesFromRigth: false,
          switchImagesFromLeft: false,
        },
        {
          path: "/home-office.png",
          text: "World",
          selected: false,
          switchLeftAnimation: false,
          switchRigtAnimation: false,
          switchImagesFromRigth: false,
          switchImagesFromLeft: false,
        },
        {
          path: "/home-office.png",
          text: "Bonjour",
          selected: false,
          switchLeftAnimation: false,
          switchRigtAnimation: false,
          switchImagesFromRigth: false,
          switchImagesFromLeft: false,
        },
      ],
      index: 0,
    };
  },
  methods: {
    switchImageLeft: function () {
      let max = this.images.length;
      this.resetAnimation(false, false, false, false, true);
      this.index = (this.index - 1 + max) % max;
      this.resetAnimation(true, true, false, false, false);
    },
    switchImageRight: function () {
      let max = this.images.length;
      this.resetAnimation(false, false, false, true, false);
      this.index = (this.index + 1) % max;
      this.resetAnimation(true, false, true, false, false);
    },
    resetAnimation(
      selected = false,
      switchImagesFromLeft = false,
      switchImagesFromRigth = false,
      switchLeftAnimation = false,
      switchRigtAnimation = false
    ) {
      this.images[this.index].selected = selected;
      this.images[this.index].switchImagesFromLeft = switchImagesFromLeft;
      this.images[this.index].switchImagesFromRigth = switchImagesFromRigth;
      this.images[this.index].switchLeftAnimation = switchLeftAnimation;
      this.images[this.index].switchRigtAnimation = switchRigtAnimation;
    },
  },
  mounted: function () {
    setInterval(
      function () {
        this.switchImageRight();
      }.bind(this),
      5000
    );
  },
};
</script>

<style lang="scss" scoped>
/**carroussel : for the container
    carroussel__chevron-left/rigth : for switching photo right and left
    carroussel__img : for the images inside the carrousel
*/

.carroussel {
  display: flex;
  position: relative;
  height: 300px;

  /*carroussel__chevron-left/rigth*/
  &__chevron-left,
  &__chevron-right {
    position: absolute;
    cursor: pointer;
    width: 7vw;
    height: 100%;
    background-color: rgba(122, 122, 122, 0.5);
    color: rgba(0, 0, 0, 0.6);
    transition-property: all;
    transition-delay: 0.4s;
    transition-timing-function: ease;

    &:hover{
      color: rgba(0, 0, 0, 0.8);
    }
  }

  &__chevron-left {
    left: 0;
    z-index: 1;
  }

  &__chevron-right {
    right: 0;
  }
}

/*carroussel__img*/
.carroussel__images {
  width: 100%;
  height: 100%;
}

.carroussel__img {
  position: relative;
  opacity: 0;

  &.selected{
    opacity: 1;
  }

  & img{
    position: absolute;
    object-fit: cover;
    object-position: 50% 50%;
    width: 100%;
    height: 300px;
    top: 0;
    left: 0;
  }
}

.img__text {
  position: absolute;
  text-align: center;
  color: white;
  font-size: 2em;
  width: 100%;
  top: 10px;
}

.switchImagesLeft,
.switchImagesFromLeft,
.switchImagesRigth,
.switchImagesFromRigth {
  animation-duration: 2s;
}

.switchImagesLeft {
  animation-name: switchImagesLeft;
  opacity: 0;
}

.switchImagesFromLeft {
  animation-name: switchImagesFromLeft;
}

.switchImagesRigth {
  animation-name: switchImagesRigth;
  opacity: 0;
}

.switchImagesFromRigth {
  animation-name: switchImagesFromRigth;
}

@keyframes switchImagesLeft {
  0% {
    opacity: 1;
  }
  100% {
    transform: translateX(-100vw);
    opacity: 0;
  }
}

@keyframes switchImagesFromLeft {
  0% {
    transform: translateX(-100vw);
    opacity: 0;
  }
  100% {
  }
}

@keyframes switchImagesRigth {
  0% {
    opacity: 1;
  }
  100% {
    transform: translateX(100vw);
    opacity: 0;
  }
}

@keyframes switchImagesFromRigth {
  0% {
    transform: translateX(100vw);
    opacity: 0;
  }
  100% {
  }
}
</style>