<template>
	<mm_page id="page_chat">
		<header>
			<mm_warp>
				<mm_container>
					<mm_row>
						<mm_col width="100">
							<mm_view url="/">
								<h3>
									<span>聊天输入栏</span>
									<span class="fr">&lt; 返回</span></router-link>
								</h3>
							</mm_view>
						</mm_col>
					</mm_row>
				</mm_container>
			</mm_warp>
		</header>
		<main>
			<mm_warp>
				<mm_container>
					<mm_row>
            <mm_col width="100">
              <button class="btn_primary" @click="show1 = true">显示代码</button>
            </mm_col>
						<mm_col width="100">
							<bar_chat :func="func_chat" v-model="val_input"></bar_chat>
							输入内容：{{val_input}}
						</mm_col>
					</mm_row>
				</mm_container>
			</mm_warp>
		</main>
    <mm_modal v-model="show1" mask="true" display="center">
      <mm_card>
        <div class="card_head">
          <span>html</span>
        </div>
        <div class="card_body">
          <expand_pre :code="code1"><code class="html"></code></expand_pre>
        </div>
        <div class="card_body">
          <span>javascript</span>
        </div>
        <div class="card_body">
          <expand_pre :code="js"><code class="javascript"></code></expand_pre>
        </div>
        <div class="card_foot">
          <mm_group><button class="btn_primary fr" @click="show1 = false">关闭代码</button></mm_group>
        </div>
      </mm_card>
    </mm_modal>
	</mm_page>
</template>

<script>
	import mixin from '@/mixins/page.js'
	export default {
		mixins: [mixin],
		data() {
			return {
        show1: false,
        code1: `<bar_chat :func="func_chat" v-model="val_input"></bar_chat>
输入内容：{{val_input}}
        `,
        js: `export default {
data() {
  return {
    val_input:"默认值"
  }
  },
  methods: {
    func_chat(o){
      console.log("page");
      console.log(o);
    },
  }
}`,
				val_input:"默认值"
			}
		},
		methods: {
			func_chat(o){
				console.log("page");
				console.log(o);
			},
		}
	}
</script>

<style>
</style>
