<template>
	<div>
		<v-pageTitle vTitle="Markdown"></v-pageTitle>
		<el-row :gutter="20">
			<el-col :xs="24" :sm="24" :md="12" :lg="12">
				<el-card class="box-card">
					<markdown-editor v-model="source" ref="markdownEditor"></markdown-editor>
				</el-card>
			</el-col>
			<el-col :xs="24" :sm="24" :md="12" :lg="12">
				<el-card class="box-card">
                    <div>预览效果：</div>
                    <markdown class="result-html full-height" :watches="['show','html','breaks','linkify','emoji','typographer','toc']"
                    :source="source" :show="show" :html="html" :breaks="breaks" :linkify="linkify"
                    :emoji="emoji" :typographer="typographer" :toc="toc"
                    toc-id="toc"></markdown>
                    <pre>
                       
                    </pre>
                </el-card>
			</el-col>
		</el-row>
	</div>
</template>
<script>
import vPageTitle from '../common/pageTitle';
import markdown  from 'vue-markdown';
import {markdownEditor} from 'vue-simplemde'
import 'simplemde/dist/simplemde.min.css';
	export default {
		name: 'Markdown',
		components: {
			markdown, markdownEditor, vPageTitle
		},
		data(){
			return {
				source: "## 可以开始编写您的Markdown文档了！",
				show: true,
                html: true,
                breaks: true,
                linkify: true,
                emoji: true,
                typographer: true,
                toc: false
			}
		}
	}
</script>
<style scoped>
	.box-card {
		line-height: 40px;
	}
</style>