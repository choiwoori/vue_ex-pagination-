<template>
    <BasicLayout :theme="'blue'">
        <div class="navigation">
            <div class="navigation__sub-menu">
                <div class="navigation__sub-menu__button-box">
                    <BasicButton v-for="item in topMenu" :key="item.label" :data="item" />
                </div>
            </div>
            <div class="navigation__sub-menu">
                <span class="navigation__sub-menu__title">Recruitment</span>
                <div class="navigation__sub-menu__button-box">
                    <BasicButton v-for="item in middleMenu" :key="item.label" :data="item" />
                </div>
            </div>
            <div class="navigation__sub-menu">
                <span class="navigation__sub-menu__title">Organization</span>
                <div class="navigation__sub-menu__button-box">
                    <BasicButton v-for="item in bottomMenu" :key="item.label" :data="item" />
                </div>
            </div>
        </div>
    </BasicLayout>
</template>

<script setup lang="ts">
import BasicLayout from '@components/atoms/layout/BasicLayout.vue'
import BasicButton from '@components/atoms/button/BasicButton.vue'
import { computed } from 'vue'

// 사실 네이밍 변수 하나만 가지고, 배열을 생성해도 되나,
// 목적상 보다 직관적으로 전달하기 위해, icon과 label로 명명 지정
const menu = [
    {
        icon: 'Dashboard',
        label: 'Dashboard',
    },
    {
        icon: 'Indox',
        label: 'Indox',
    },
    {
        icon: 'Calendar',
        label: 'Calendar',
    },
    {
        icon: 'Jobs',
        label: 'Jobs',
    },
    {
        icon: 'Reference',
        label: 'Reference',
    },
    {
        icon: 'Document',
        label: 'Document',
    },
    {
        icon: 'CareerSite',
        label: 'CareerSite',
    },
    {
        icon: 'Employee',
        label: 'Employee',
    },
    {
        icon: 'Structure',
        label: 'Structure',
    },
    {
        icon: 'Settings',
        label: 'Settings',
    },
]

//Computed : 계산된 형태의 데이터를 가공하기 때문에 & 반드시 return 시켜주어야 한다.
const topMenu = computed(() => {
    return menu.slice(0, 3)
})
const middleMenu = computed(() => {
    return menu.slice(3, 7)
})
const bottomMenu = computed(() => {
    return menu.slice(7, menu.length)
})
</script>

<style lang="scss" scoped>
.navigation {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;

    width: 100%;

    gap: 40px;

    &__sub-menu {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;

        width: 100%;

        &__title {
            margin-bottom: 12px;

            font-family: 'SUITE-Regular';
            color: $color-white-000;
        }
        &__button-box {
            width: calc(100% - 24px);
        }
    }
}
</style>