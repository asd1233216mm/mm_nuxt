<template>
  <!-- 图片 -->
  <mm_page id="expand_drag">
    <header class="header">
      <mm_warp>
        <mm_container>
          <mm_row>
            <mm_col width="100">
              <mm_view url="/">
                <h3>
                  <span>图片</span>
                  <span class="fr">&lt; 返回</span></router-link>
                </h3>
              </mm_view>
            </mm_col>
          </mm_row>
        </mm_container>
      </mm_warp>
    </header>
    <main style="overflow: auto; min-height: calc(100vh - 5rem);">
      <mm_warp>
        <mm_container>
          <mm_row>
            <mm_col width="100">
              <expand_drag id="drag_1" :pos="obj.pos">请拖动我1！</expand_drag>
              <expand_drag id="drag_2" :pos="obj2.pos">请拖动我2！</expand_drag>
            </mm_col>
            <mm_col width="100">
              <button class="btn_primary" @click="show1 = true">显示代码</button>
            </mm_col>
            <mm_col width="100">
              {{ obj }}
            </mm_col>
              <mm_col width="100" style="height: 50px;">
              </mm_col>
            <mm_col width="100">
              <button class="btn_primary" @click="show2 = true">显示代码</button>
            </mm_col>
            <mm_col width="100">
              {{ obj2 }}
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
      <mm_modal v-model="show2" mask="true" display="center">
        <mm_card>
          <div class="card_head">
            <span>html</span>
          </div>
          <div class="card_body">
            <expand_pre :code="code2"><code class="html"></code></expand_pre>
          </div>
          <div class="card_body">
            <span>javascript</span>
          </div>
          <div class="card_body">
            <expand_pre :code="js2"><code class="javascript"></code></expand_pre>
          </div>
          <div class="card_foot">
            <mm_group><button class="btn_primary fr" @click="show2 = false">关闭代码</button></mm_group>
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
        code1: `<expand_drag id="drag_1" :pos="obj.pos">请拖动我1！</expand_drag>`,
        js1:`export default {
  data() {
    return {
      obj: {
        pos: {
          x: 0,
          y: 100
        }
      }
    }
  }
}`,
        show2: false,
        code2: `<expand_drag id="drag_2" :pos="obj2.pos">请拖动我2！</expand_drag>`,
        js2:`export default {
  data() {
    return {
      obj2: {
        pos: {
          x: 0,
          y: 100
        }
      }
    }
  }
}`,
        obj: {
          pos: {
            x: 0,
            y: 100
          }
        },
        obj2: {
          pos: {
            x: 0,
            y: 200
          }
        }
      }
    }
  }
</script>

<style>
</style>
