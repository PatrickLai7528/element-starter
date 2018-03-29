<template>
    <el-container class = "basicGlobalStyle">
        <el-aside>
            <ac-menu></ac-menu>
        </el-aside>
        <el-main>
            <ac-display></ac-display>
        </el-main>
    </el-container>
</template>

<script>
    import acMenu from './assets/components/ac-menu.vue';
    import acDisplay from './assets/components/ac-display.vue';

    export default {
        components: {
            acMenu,
            acDisplay
        },
        data() {
            return {
                currentDate: new Date(),
                dialogVisible: false
            };
        },
        methods: {
            handleClose(done) {
                this.$confirm('确认关闭？')
                    .then(_ => {
                        done();
                    })
                    .catch(_ => {
                    });
            }
        }
    }
</script>

<style>
    .basicGlobalStyle{
        font-family: Microsoft YaHei;
    }
</style>
