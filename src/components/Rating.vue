<template>
  <div >
    <i class="fas fa-star" :class="this.color"></i>
    <i class="fas fa-star" :class="this.color"></i>
    <i class="fas fa-star" :class="this.color"></i>
    <i class="fas fa-star-half-alt" :class="this.color"></i>
    <i class="far fa-star" :class="this.color"></i>
  </div>
</template>

<script>
export default {
    name: "Rating",
    props: {
        star:Number,
        color:String,
    }
  }
</script>

<style scoped>
.pink{
    color:#C3A1A0;
}
.blue{
    color:#7ccde6;
}
i{

    margin-bottom: 10px;
}
</style>