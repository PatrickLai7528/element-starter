<template>
    <div>
        <el-menu default-active="1-4-1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose"
        >
            <el-menu-item index="0">
                <!--Award Chaser -->
                <img src="../images/awardchaser-logo.jpg" height="100%" style="alignment: center">
            </el-menu-item>
            <el-submenu index="1">
                <template slot="title">
                    <i class="el-icon-location"></i>
                    <span slot="title">比賽分類</span>
                </template>
                <el-menu-item index="1-1">徵文/作文</el-menu-item>
                <el-menu-item index="1-2">微電影/短片</el-menu-item>
                <el-menu-item index="1-3">攝影</el-menu-item>
                <el-menu-item index="1-4">設計</el-menu-item>
                <el-menu-item index="1-5">現場問答</el-menu-item>
                <el-menu-item index="1-6">體育/運動</el-menu-item>
            </el-submenu>
            <el-menu-item index="2">
                <i class="el-icon-menu"></i>
                <span slot="title">發佈比賽</span>
            </el-menu-item>
            <el-menu-item index="3">
                <i class="el-icon-document"></i>
                <span slot="title">關於</span>
            </el-menu-item>
        </el-menu>
    </div>
</template>

<script>
    export default {
        data() {
            return {}
        },
        methods: {
            handleOpen(key, keyPath) {
                console.log(key, keyPath);
            },
            handleClose(key, keyPath) {
                console.log(key, keyPath);
            },
        }
    }
</script>

<style scoped>

</style>