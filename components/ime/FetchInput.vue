<script setup lang="ts">
import * as utils from './share'
import { onMounted, shallowRef, ref } from "vue";
import InputMethod from './InputMethod.vue'

const p = defineProps<{
    /** 码表文件的URL */
    mabiaoUrl: string
    /** 方案的ID，用于保存localstorage */
    id?: string
    /** 方案的配置 */
    //rule: utils.ImeRule
}>()

const mabiaoList = shallowRef<utils.MabiaoItem[]>()

const progress = ref({ max: 0, current: 0 })

onMounted(async () => {
    mabiaoList.value = await utils.fetchMabiao(p.mabiaoUrl, progress)
})

</script>

<template>
    <div class="text-gray-600 text-center mt-10" v-if="!mabiaoList">
        <div class="text-center">下载码表……</div>
        <progress class="progress progress-info w-full max-w-screen-sm" :value="progress.current"
            :max="progress.max"></progress>
    </div>
    <InputMethod v-else :id="id || mabiaoUrl" :rule="utils.YuhaoRule" :data="mabiaoList">
        <slot></slot>
    </InputMethod>
</template>
