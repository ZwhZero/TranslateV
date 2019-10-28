<template>
  <div class="row fcenter" id="translateForm">
  	<div class="fcenter">
  		<!--使用form-inline让子节点中文本框一行排列，不单独占行-->
      <form class="well form-inline" v-on:submit="formSubmit" role="form">
        <input class="form-control" type="text" v-model="textToTranslate" placeholder="输入需要翻译的内容"/>
        <select class="form-control" v-model="language">
      	  <option value="en">English</option>
      	  <option value="ru">Russian</option>
      	  <option value="ko">Korean</option>
      	  <option value="ja">Japanese</option>
        </select>
        <input class="btn btn-secondary" type="submit" value="翻译" />
      </form>
    </div>
  </div>
</template>

<script>

export default {
  name: 'translateForm',
  data:function(){
  	return {
  	  textToTranslate:"",
  	  language:""
  	}
  },
  methods:{
  	formSubmit:function(e){
//	  alert(this.textToTranslate);
  	  this.$emit("formToApp",this.textToTranslate,this.language);	//组件注册事件且传值
  	  e.preventDefault();	//取消默认事件：翻译后刷新
  	}
  },
  created:function(){
  	this.language = "en";
  }
}
</script>

<style>
	#translateForm{
		text-align: center;
		border: 1px #ccc solid;
		border-radius: 10px;
	}
	.fcenter{
		display: flex;
		justify-content: center;
	}
</style>
