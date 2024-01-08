<template>
    <div class="list">
        <div class="list__avatar">
            <img src="" alt="" class="list__avatar__image">
            <div class="list__avatar__text-box">
                <span class="name">Marce</span>
                <span class="duty">User Experience</span>
            </div>
        </div>
        <div class="list__item"></div>
        <div class="list__item"></div>
        <div class="list__item">
            <div class="list__item__chip">Senior</div>
        </div>
    </div>
</template>

<script setup lang="ts">

</script>

<style lang="scss" scoped>
.list{
    display: flex;
    align-items: center;

    width: calc(100% - 32px);
    height: 72px;
    min-height: 72px;

    padding: 0 16px;
    gap: 24px;

    background-color: rgba($color-white-200, 0.1);
    border-radius: 16px;
}
</style>