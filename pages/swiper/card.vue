<template>
  <mm_page id="page_card">
    <header class="header">
      <mm_warp>
        <mm_container>
          <mm_row>
            <mm_col width="100">
              <mm_view url="/">
                <h3>
                  <span>轮播卡片</span>
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
              <h5>默认块</h5>
              <swiper_card :list="list">
                <template slot-scope="scope">
                  <div class="info">
                    <a :href="scope.row.url">
                      <p>标题:{{scope.row.title}}</p>
                      <img :src="scope.row.image" alt="">
                    </a>
                  </div>
                </template>
              </swiper_card>
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
        code1: `<swiper_card :list="list">
	<template slot-scope="scope">
		<div class="info">
			<a :href="scope.row.url">
				<p>标题:{{scope.row.title}}</p>
				<img :src="scope.row.image" alt="">
			</a>
		</div>
	</template>
</swiper_card>`,
        js1: `export default {
	data(){
	list: [{
			title: "标题",
			url: "/",
			image: "/img/default.png",
		},
		{
			title: "标题",
			url: "/",
			image: "/img/default.png",
		},
		{
			title: "标题",
			url: "/",
			image: "/img/default.png",
		}
	]}
}`,
        list: [{
            title: "标题",
            url: "/",
            image: "/img/default.png",
          },
          {
            title: "标题",
            url: "/",
            image: "/img/default.png",
          },
          {
            title: "标题",
            url: "/",
            image: "/img/default.png",
          }
        ]
      }
    }
  }
</script>

<style>
</style>
