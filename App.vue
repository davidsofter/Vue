/* eslint-disable */
<template>
  <div id="app">
		<header class='site-header jumbotron'>
			<div class='container'>
				<div class='row'>
					<div class='col-xs-12'>
						<h1>请发表你对Vue的评论</h1>
					</div>
				</div>
			</div>
		</header>
    <!-- <img src="./assets/logo.png"> -->
		<Add :addComment='addComment'/>		<!-- 按表达式将方法传递到子组件 -->
		<List :comments='comments' :deleteComment='deleteComment'/>			<!-- 按表达式将方法传递到子组件 -->
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Add from './components/Add'
import List from './components/List'
import Item from './components/Item'

export default {
  name: 'App',
	data(){
		return{ 
			comments:[
				{
					name: 'Bob',
					content: 'Vue还不错',
				},
				{
					name: 'Kate',
					content: 'Vue so easy',
				},
				{
					name: 'banz',
					content: 'Vue so so',
				},
			]
		}
	},
	methods:{//数据写在哪一页，数据相关的方法就写在那一页
		//添加评论
		addComment(comment){
			this.comments.unshift(comment)
		},
		
		//删除指定下标的评论
		deleteComment(index){
			this.comments.splice(index,1)
		}
	},
  components: {
		Add,
		List,
		Item
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
