<template>
    <div class="wizard__header">
        <ul class="wizard__step">
            <li class="step__list">
            <a href="javascript:void(0);">
                <div class="list__item list__item--active">
                1
                </div>
                Delivery
            </a>
            </li>
            <li class="step__list">
            <a href="javascript:void(0);">
                <div class="list__item">
                2
                </div>
                Payment
            </a>
            </li>
            <li class="step__list">
            <a href="javascript:void(0);">
                <div class="list__item">
                3
                </div>
                Finish
            </a>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "WizardHeader"
}
</script>

<style lang="stylus" scoped>

</style>
