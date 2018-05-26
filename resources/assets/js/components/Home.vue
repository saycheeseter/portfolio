<template>
    <div class="home__center">
        <header-front></header-front>
    </div>

</template>

<script>

import Header from './main/Header';
export default {
    data:{
        
    },
    components: {
        'header-front': Header,
    }

}
</script>


<style lang="scss">
.home__center{
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>
