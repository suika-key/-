<template>
  <div>
    <div class="header">
        <div class="header_left">
            <div class="text_dec">RDR</div>
            <div class="select_work_plat"><WorkDropMeau/></div>
        </div>
        <div class="header_right">
            <div class="module_name">
                <ModuleDropMeau/>
            </div>
            <div class="right_icon"><BellOutlined /> </div>
            <div class="right_meau">name <UnorderedListOutlined /></div>
        </div>
    </div>
    <div class="main">
        <div class="main_left_slider">
            <div class="main_left_slider_header"><user-outlined />角色选择</div>
            <div class="main_left_slider_content">
                <!-- <div v-for="(item,index) in sliderMeauData" :key="index">
                    <component :is="sliderMeauIcon[index]"></component>
                    <span>{{item}}</span>
                </div> -->
                <div @click="changeIsShow(0)">
                    <user-outlined />
                    <span>产品设计</span>
                    
                </div>
                <div @click="changeIsShow(1)">
                    <user-outlined />
                    <span>技术研发</span>

                </div>
                <div @click="changeIsShow(2)">
                    <user-outlined />
                    <span>测试验收</span>

                </div>
            </div>

        </div>
        <div class="second_meau" v-if='isShow'>
            <SecondMeau :secondArr='secondArr'/>
        </div>
        <div class="main_content">
            <div class="main_content_one">RDR问题预设</div>
            <div class="main_content_two">
                <div class="main_content_two_item" v-for="(item,index) in problemArr" :key="index">
                    {{item}}
                </div>
            </div>
            <div class="main_content_three">
                <input id="inp" type="text" placeholder="请输入内容"/>
                <div class="inp_icon"><BellOutlined :style="{fontSize : '26px'}"></BellOutlined></div>
            </div>
        </div>
        <div class="main_right_slider">
            <RightSlider></RightSlider>
        </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import {ref} from 'vue'
import WorkDropMeau from './components/WorkDropMeau.vue'
import ModuleDropMeau from './components/ModuleDropMeau.vue'
import SecondMeau from './components/SecondMeau.vue'
import RightSlider from './components/RightSlider.vue'
import { BellOutlined , UnorderedListOutlined ,UserOutlined} from '@ant-design/icons-vue';

// const sliderMeauData=['产品设计','技术研发','测试验收']
// const sliderMeauIcon=['UnorderedListOutlined','UnorderedListOutlined','UnorderedListOutlined']
let isShow = ref(false)
let secondArr=ref([])
let problemArr = ref([1,2,3,4,5,6,7,8,9])

const changeIsShow = (arg)=>{
    // console.log(arg);
    if (arg == 0) {
        secondArr.value = ['原型图','流程图','思维导图','设计图'] 
        isShow.value = !isShow.value
    }else if(arg == 1){
        secondArr.value = ['Java','HTML','Python','Mango'] 
        isShow.value = !isShow.value
    }else{
        isShow.value = false
    }
    
}

</script>

<style scoped>

 ::v-deep .ant-dropdown-link{
        color: white;
    }
.header{
    width: 100%;
    height: 50px;
    display: flex;
    color: white;
    justify-content: space-between;
    background-color: rgb(102, 102, 102);
    padding: 0 20px  0 30px;
}
.header_left,.header_right{
    /* width: 200px; */
    display: flex;
    justify-content: flex-start;
    align-items: center;
   
}
.text_dec{
        font-family: Roboto;
    font-weight: 400;
    font-size: 17px;
    position: relative;
}
.text_dec::after{
    width: 1px;
    height: 17px;
    position: absolute;
    content: '';
    
    background-color: aliceblue;
    left: 50px;
    top: 3px;
}
.select_work_plat{
    margin-left: 30px;
}
.right_icon{
    margin: 0 20px;
}

.main{
    background: rgb(239, 239, 239);
    height: 877px;
    display: flex;
}
.main_left_slider{
    width: 224px;
    height: 100%;
    background-color: white;
     border-right: 1px solid rgb(187, 187, 187);
}
.main_left_slider_header{
    height: 49px;
    font-size: 20px;
    line-height: 49px;
    border-bottom: 1px solid;
    padding-left: 30px;
        border-color: rgb(187, 187, 187);
}
.main_left_slider_content{
    padding-left: 30px;
}
.main_left_slider_content div{
    height: 49px;
    line-height: 49px;
}
.second_meau{
    position: fixed;
    height: 100%;
    left: 140px;
}
.main_content{
    width: 100%;
}
.main_content_one{
    width: 100%;
    font-size: 30px;
    text-align: center;
    margin-top: 100px;
}
.main_content_two{
    /* margin-top:100px ; */
    display: flex;
    flex-wrap: wrap;
    width: 800px;
    margin: 100px auto;
}
.main_content_two_item{
    width: 200px;
    height: 100px;
     border: 1px solid rgb(187, 187, 187);
         border-radius: 14px;
         margin-left: 50px;
         margin-top: 30px;
         background-color: white;
}
.main_content_three{
    /* margin: 0 auto; */
    width: 100%;
    display: flex;
    justify-content: center;
    position: relative;
}
.inp_icon{
    position: absolute;
    right: 390px;
    top: 10px;
}
#inp {
    width: 800px;
    height: 50px;
    outline: none;
    border: none;
}

.main_right_slider{
    /* width: 138px; */
    height: 100%;
    background-color: white;
}
</style>