<template>
	<el-config-provider :locale="zhCn">
		<div class="w-full h-screen overflow-x-hidden overflow-y-auto">
			<el-scrollbar>
				<div
					class="w-full h-16 bg-rose-100/50 shadow-sm sticky left-0 top-0 backdrop-blur-sm z-10"
				>
					<div class="mx-auto max-w-6xl px-4 h-full flex items-center">
						<img src="/img.jpg" class="w-8 h-8 block mr-2" />
						<div class="text-lg">
							{{ appName }}
						</div>
						<div class="flex-1"></div>

						<div
							:class="{
								'bg-rose-300': $route.path === '/up'
							}"
							class="px-3 py-2 rounded-md mr-2 text-gray-800 text-sm cursor-pointer"
							@click="router.push('/up')"
						>
							<font-awesome-icon :icon="faUpload" :class="[$route.path === '/up' ? 'text-white' : 'text-gray-500']" />
							<span class="hidden md:inline-block pl-2">上传</span>
						</div>

						<div
							:class="{
								'bg-rose-300': $route.path === '/'
							}"
							class="px-3 py-2 rounded-md text-gray-800 text-sm cursor-pointer"
							@click="router.push('/')"
						>
							<font-awesome-icon :icon="faCog" :class="[$route.path === '/' ? 'text-white' : 'text-gray-500']" />
							<span class="hidden md:inline-block pl-2">管理</span>
						</div>
					</div>
				</div>

				<div class="min-h-[calc(100vh-64px-64px)] overflow-auto">
					<router-view />
				</div>

			</el-scrollbar>
		</div>
	</el-config-provider>
</template>

<script setup lang="ts">
import { faCog, faUpload } from '@fortawesome/free-solid-svg-icons'
import { useRouter } from 'vue-router'
import { ElScrollbar, ElConfigProvider } from 'element-plus'
import zhCn from "element-plus/es/locale/lang/zh-cn"

	
const appName = 'Pinhaa'

document.title = appName

const router = useRouter()
</script>
