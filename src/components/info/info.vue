<template>
    <div id="infor" class="layouts">

        <div class="infor_header">

        <div class="arrow" @click="routerBack">
            <router-link to="/">
            <img :src="src" />
            </router-link>

        </div>

        <h1>{{message}}</h1>
        </div>


        <ul>
            <li>
            <div class="active_img">


                <div class="active_photo">
                <img src="static/images/title.png"/>
                </div>
                <div class="active_title"> 头像 </div>


            </div>
            </li>


            <li v-for="user in users" class="user_li">

               <label class="front"> {{user.name}}</label>


                <input type="text" name="" :value="user.value" class="user_input">



            </li>


            <!--

<li class="size_body">身体数据</li>
            <li v-for="size in sizes" class="user_li">

                <label class="front"> {{size.name}}</label>


                <input type="text" name="" :value="size.value" class="user_input">



            </li>


            <li>
                穿衣习惯
            <input type="radio" id="one" value="One">
            <label for="one">修身</label>

            <input type="radio" id="two" value="Two">
            <label for="two">舒适</label>
            </li>
            -->

        </ul>

        <div class="submit"><button class="submit_button">提交</button></div>
    </div>
</template>

<script>

    export default {
        name: 'infor',
        data(){
            return{
                message:'个人信息',

                users:[


                    {name: '昵称',value:'赖连庄'},
                    {name: '性别',value:'男'},
                    {name: '手机号码',value:'18815154008'},
                    {name: '电子邮箱',value:'请输入电子邮箱'},
                    {name: '生日',value:'请输入生日'}
                ],


                sizes:[


                    {name: '身高',value:'174CM'},
                    {name: '体重KG',value:'70KG'},
                    {name: '中腰CM',value:'32英寸/82.5CM'},

                ],

                src:"static/images/arrow.png",


            }
        },

        mounted: function () {
            this.bus.$emit('hide');
        },
        methods:{

            routerBack(){
                 this.bus.$emit('show');
                //this.$router.back(-1);

            }

        }
    }
</script>

<style>
    #info {

    }
</style>
