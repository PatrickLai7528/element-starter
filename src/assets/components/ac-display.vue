<template>
    <div>
        <el-row>
            <el-col style="padding-bottom: 10px" :span="6" v-for="(image, index) in images" :key="image"
                    :offset=" ( ( index + 1 ) % 3 != 1  ) ? 2 : 0">
                <el-card :body-style="{ padding: '0px' }">
                    <img :src="image.path" class="image">
                    <div style="padding: 14px;">
                        <span>{{ image.desc }}</span>
                        <div class="bottom clearfix">
                            <time class="time">{{ image.ddl }}</time>
                            <el-button type="text" class="button" @click="checkMore(index)">查看更多</el-button>
                        </div>
                    </div>
                </el-card>
            </el-col>
        </el-row>
        <el-dialog
                :title="images[selectedImageId].title"
                :visible.sync="dialogVisible"
                width="30%"
        >
            <span>{{images[selectedImageId].desc}}</span>
            <span slot="footer" class="dialog-footer">
                <el-button @click="dialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                dialogVisible: false,
                selectedImageId: 0,
                images: [
                    {
                        title: "吃漢堡包大賽1",
                        path: "src/assets/images/hamburger.png",
                        desc: "吃漢堡包大賽1",
                        ddl: "2018/09/10",

                    },
                    {
                        title: "吃漢堡包大賽2",
                        path: "src/assets/images/hamburger.png",
                        desc: "吃漢堡包大賽2",
                        ddl: "2018/09/10",

                    },
                    {
                        title: "吃漢堡包大賽3",
                        path: "src/assets/images/hamburger.png",
                        desc: "吃漢堡包大賽3",
                        ddl: "2018/09/10",

                    },
                    {
                        title: "吃漢堡包大賽4",
                        path: "src/assets/images/hamburger.png",
                        desc: "吃漢堡包大賽4",
                        ddl: "2018/09/10",

                    },
                ]
            }
        },
        methods: {
            checkMore(index) {
                this.dialogVisible = true;
                if (index >= 0 && index < this.images.length) {
                    this.selectedImageId = index;
                } else {
                    console.log("index out of bound");
                }
            }
        }
    }
</script>

<style scoped>
    .time {
        font-size: 13px;
        color: #999;
    }

    .bottom {
        margin-top: 13px;
        line-height: 12px;
    }

    .button {
        padding: 0;
        float: right;
    }

    .image {
        width: 100%;
        display: block;
    }

    .clearfix:before,
    .clearfix:after {
        display: table;
        content: "";
    }

    .clearfix:after {
        clear: both
    }

    .el-menu-vertical-demo:not(.el-menu--collapse) {
        width: 200px;
        min-height: 400px;
    }
</style>