<template>
  <div id="app">
	  <div class="header">
		  <div class="btn" @click="isPreview=!isPreview">
		  		{{isPreview?'编辑':'预览'}}
		  </div>
		   <div class="btn" @click="isMobile=!isMobile">
		  		{{isMobile?'Pc':'Phone'}}
		  </div>
	  </div>
    <vue-amis-sdk
        id='editorName'
        theme='cxd'
        className='is-fixed'
        :isPreview='isPreview'
        :isMobile='isMobile'
        @change='onChange'
        :value='schema'
    />
  </div>
</template>
<script>
import VueAmisSdk from 'vue-amis-sdk'
import 'vue-amis-sdk/lib/vue-amis-sdk.css'

export default {
  name: 'App',
  data() {
    return {
      isPreview: false,
      isMobile: false,
      schema:{
  "type": "page",
  "title": "23232",
  "body": [
    {
      "type": "form",
      "title": "表单",
      "body": [
        {
          "label": "文本框文本框文本框文本框",
          "type": "input-text",
          "name": "text",
          "id": "u:05a2a8b17444"
        }
      ],
      "id": "u:977658ae7520",
      "rules": [
      ],
      "submitText": "提交",
      "actions": [
        {
          "type": "button-group",
          "id": "u:85beb2f89589"
        }
      ],
      "mode": "horizontal"
    }
  ],
  "id": "u:2ee616f71890",
  "aside": [
  ],
  "regions": [
    "body"
  ],
  "pullRefresh": {
    "disabled": true
  },
  "asideResizor": false,
  "asideSticky": true
}
    }
  },
  components: {
    VueAmisSdk: window.VueAmisSdk
  },
  methods: {
    onChange(e) {
      console.log(e)
    }
  }
}
</script>

<style scoped>
::v-deep .is-fixed{
	top:52px;
}
.header{
	border-bottom:1px solid #d4d6d9;
	padding: 10px 40px;
	width: 100%;
	box-sizing: border-box;
	display: flex;
	justify-content: center;
}
.btn{
	border-radius: 4px;
	background: rgb(64,158,255);
	padding:0 10px;
	cursor: pointer;
	color:#fff;
	line-height: 30px;
}
.btn:nth-child(2){
	margin-left: 100px;
}
</style>
