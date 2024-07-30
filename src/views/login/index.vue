<script lang="ts" setup>

import { ref } from 'vue'
import LoginPageBannerImgUrl from "@/assets/login_bg.jpg"
import captchaImg from "@/assets/captcha.jpg"

const loginPageBanner = ref(LoginPageBannerImgUrl)

const ruleForm = ref({
    checkPass: "",
    captcha: ""
})

</script>
<template>
    <el-row class="bannerWrapper">
        <el-col :span="14" class="bannerDiv">
            <img class="bannerImg" :src="loginPageBanner" />
        </el-col>
        <el-col :span="10">
            <el-row type="flex">
                <el-card body-class="cardWrapper">
                    <template #header>
                        <div class="card-header">
                            <h2>Time Capsule 画廊入口</h2>
                        </div>
                    </template>
                    <el-row>
                        <el-form label-position="right" label-width="120px">
                            <el-form-item label="口令" prop="checkPass">
                                <el-input style="width: 460px;" v-model="ruleForm.checkPass" type="password"
                                    autocomplete="off" />
                            </el-form-item>
                            <el-form-item label="验证码" prop="captcha">
                                <div class="captcha-wrapper">
                                    <el-input style="width: 300px;" v-model="ruleForm.captcha" type="text"
                                        autocomplete="off" />
                                    <img :src="captchaImg" style="width: 140px;" />
                                </div>
                            </el-form-item>
                            <el-form-item>
                                <el-button>提交</el-button>
                            </el-form-item>
                        </el-form>
                    </el-row>
                    <template #footer>
                        <div class="card-header">
                            常回来看看！
                        </div>
                    </template>
                </el-card>
            </el-row>
        </el-col>
    </el-row>
</template>

<style lang="scss">
.bannerWrapper {
    width: 100%;
    height: 100vh;
    margin: 0 auto;
    justify-content: center;
    align-items: center;

    .bannerDiv {
        width: 100%;
        padding: 2%;
        max-width: 1000px;

        .bannerImg {
            width: 100%;
        }
    }

    .card-header {
        text-align: center;
    }

    .cardWrapper {
        width: 100%;
        min-width: 700px;

        .captcha-wrapper {
            display: flex;
            width: 100%;
            justify-content: space-between;
        }
    }
}
</style>