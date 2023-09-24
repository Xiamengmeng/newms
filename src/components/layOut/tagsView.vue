<template>
<div class="tags">
    <ul class="tags-list">
        <li class="tags-item" ref="tag" v-for="(item,index) in visitedviews" :key="item.path" :class="isActive(item.path)?'active':''">
            <router-link tag="span" :to="{path:item.path}">{{ item.title }}
                <span v-if="!isAffix(item)" class="close-btn el-icon-close" @click.prevent.stop="closeSelectedTag(index)"></span>
            </router-link>
        </li>
    </ul>
    <ul v-show="contentMenuVisbile" :style="{left:left+'px',top:top+'px'}" class="context-menu">
        <li @click="closeSelectedTag(selectedIndex)">关闭</li>
    </ul>
    
</div>
</template>
<script>
    export default {
        data(){
            return{
                top:0,
                left:0,
                visitedviews:[{path:'/helloWorld',title:'首页'}],
                contentMenuVisbile:false,
                selectedIndex:''
            }
        },
        methods:{
            // 是否当前标签页
            isActive(path){
                return true;
            },
            isAffix(item){
                return false;
            },
            closeSelectedTag(index){
                // 关闭标签

            }
        }
    }
</script>
<style lang="" scoped>
    .tags {
        position:relative;
        display:flex;
        margin:0 20px;
        padding:20px 0;
        justify-content:space-between;
        align-items:center;
        border-bottom:1px solid #ccc;
        z-index:100;
        &-item{
            display:inline-block;
            font-size:14px;
            color:#666;
            padding:0 10px;
            border-right:1px sollid #ddd;
            cursor:pointer;
            &.active{
                color:#396fff;
            }
            &:hover{
                .close-btn{
                    display:inline-block;
                    opacity:1;
                }
            }
            .close-btn{
                display:none;
                opacity:0;
            }
        }
        &-other{
            width:32px;
            height:32px;
            text-align:center;
            i{
                font-size:24px;
            }
        }

    }
</style>