<template>
  <mm_page id="page_chat">
    <header class="header">
      <mm_warp>
        <mm_container>
          <mm_row>
            <mm_col width="100">
              <mm_view url="/">
                <h3>
                  <span>底部导航</span>
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
              <mm_view>
                <nav_bottom>
                </nav_bottom>
              </mm_view>
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
          <expand_pre :code="js1"><code class="javascript"></code></expand_pre>
        </div>
        <div class="card_foot">
          <mm_group><button class="btn_primary fr" @click="show1 = false">关闭代码</button></mm_group>
        </div>
      </mm_card>
    </mm_modal>
  </mm_page>
</template>

<script>
  export default {
    data() {
      return {
        show1: false,
        code1: `<nav_bottom></nav_bottom>`,
        js1: `export default {
	data(){
	list: [
	  {
	    title: "新浪简介",
	    url: ""
	  }
	]
	}
}`,
        select: 0,
        col: 2,
        options: [{
            name: "1列",
            value: "1"
          },
          {
            name: "2列",
            value: "2"
          },
          {
            name: "3列",
            value: "3"
          },
          {
            name: "4列",
            value: "4"
          },
          {
            name: "5列",
            value: "5"
          },
          {
            name: "6列",
            value: "6"
          },
          {
            name: "8列",
            value: "8"
          },
          {
            name: "10列",
            value: "10"
          },
          {
            name: "12列",
            value: "12"
          }
        ],
        list: undefined
      }
    },
  }
</script>

<style scoped="scoped">
</style>
