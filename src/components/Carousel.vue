<template>
<div>
<!-- Display of Images -->
<div class=" w-full mt-24 lg:inline-flex md: inline-flex overflow-hidden bg-grey-lighter">
    <div v-for="(image, index) in filteredImages" :key="index" class="overflow-hidden ml-auto mr-auto">
        <img :src="image.src" :alt="image.alt" class="lg: max-w-md w-auto h-48"  />
    </div>
</div>

<!--Interactive Selection of Images -->
<div class="flex justify-center mt-4">
    <div class="rounded w-2 h-2 bg-grey ml-1 mr-1" v-for="(n, index) in images.length" :class="index == showIndex ? 'bg-gold':''" :key="index" @click="showIndex = index">
    </div>
</div>
</div>

</template>

<script>
export default{
    props: ['sm','lg'],
    data() {
        return {
            showIndex: 0,
            images: [
                { src: './1.jpg', alt: 'mt fuji'},
                { src: '2.jpg', alt: 'mt fuji temple'},
                {src: '3.jpg', alt: 'mt fuji temple closeup'},
                { src: './1.jpg', alt: 'mt fuji'},
                { src: '2.jpg', alt: 'mt fuji temple'},
                {src: '3.jpg', alt: 'mt fuji temple closeup'}
            ]
        }
    },
    computed: {
        filteredImages() {
            let newImageArray = []
            let noOfImage = this.$mq === 'sm' ? this.sm : this.lg
            newImageArray = this.images.slice(this.showIndex, this.showIndex+noOfImage)
            console.log(newImageArray)
            return newImageArray
        }
    }
}
</script>

<style>
.slide-fade-enter-active {
  transition: all .3s ease;
}
.slide-fade-leave-active {
  transition: all .8s cubic-bezier(1.0, 0.5, 0.8, 1.0);
}
.slide-fade-enter, .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>