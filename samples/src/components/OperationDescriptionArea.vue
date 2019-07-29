<template>
<div class="p-operation-area">
  <div class="p-left-block">
    <ul class="p-tab-items">
      <li @click="selectTab(DEFAULT_TAB)"
          :class="[selectedTab === DEFAULT_TAB ? 'is-active' : '',
                  'p-tab-item']">Introduction</li>
      <li v-for="dataSet in dataSets"
          :key="dataSet.id"
           @click="selectTab(dataSet.id)"
          :class="[selectedTab === dataSet.id ? 'is-active' : '',
                  'p-tab-item']">{{ dataSet.name }}</li>
    </ul>
    <div class="p-left-block-inner">
      <div class="p-tab-contents">
        <div class="p-tab-content" v-show="selectedTab === DEFAULT_TAB">
          <div class="p-block-inner">
            <h3>{{ descriptionTitle }}</h3>
            <p id="operation-description" class="markdown-body" />
          </div>
        </div>
        <div class="p-tab-content" v-if="selectedTab !== DEFAULT_TAB">
          <div class="p-block-inner">
            <div class="p-tab-content-description">
              {{ dataSet.find(e => e.id === selectedTab).content }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
</template>
<script>
import marked from 'marked';
import hljs from 'highlightjs';
export default {
  name: 'operation-description',
  props: {
    descriptionTitle: {
      type: String,
      required: true
    },
    operationDescription: {
      type: String,
      required: true
    },
    dataSets: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      DEFAULT_TAB: 'DEFAULT_TAB',
      selectedTab: 'DEFAULT_TAB'
    }
  },
  mounted() {
    MathJax.Hub.Config({
      skipStartupTypeset: true, // ページロード時のmathjax発動禁止
      extensions: ["tex2jax.js"],
      jax: ["input/TeX", "output/HTML-CSS"],
      tex2jax: {
        inlineMath: [ ['$','$'], ["\\(","\\)"] ],
        displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
        processEscapes: true
      },
      "HTML-CSS": {
        availableFonts: ["TeX"]
      }
    })
    marked.setOptions({
      renderer: new marked.Renderer(),
      gfm: true,
      tables: true,
      breaks: true,
      pedantic: false,
      sanitize: false,
      smartLists: false,
      smartypants: false,
      highlight: function(code, lang) {
        return hljs.highlightAuto(code, [lang]).value
      }
    })
  
    const text = this.operationDescription
    console.log('text', text)
    
    // markedにlatexタグ食わせると&<>とかがエスケープされるのでPREFIX ~ SUFFIXで包んで退避
    const PREFIX = "<pre><code class=\"lang-math-quest-operation\">";
    const SUFFIX = "</code></pre>";
    const reg = new RegExp(
      ("(?:" + PREFIX + "([\\s\\S]*?)" + SUFFIX + ")")
        .replace(/\//g, "\/"),
      "gm");
    const wraped = text.split("$$")
      .reduce(function(sum, str, i){
        return i % 2 === 0 ?
                sum + str :
                sum + PREFIX + str + SUFFIX;
      }, "");
    const html = marked(wraped);
    // 退避したlatexタグを$$で包み直す
    let _html = html;
    let tuple = null;
    while(tuple = reg.exec(html)){
      _html = _html.split(tuple[0]).join("$$" + tuple[1] + "$$");
    }
    // mathjaxで処理
    const compiledMarkdown = document.getElementById("operation-description");
    compiledMarkdown.innerHTML = _html;
    MathJax.Hub.Configured();
    MathJax.Hub.Queue(["Typeset", MathJax.Hub, compiledMarkdown]);
  },
  methods: {
    selectTab(tabId) {
      this.selectedTab = tabId
    }
  }
}
</script>
<style lang="scss" scoped>
@import '~github-markdown-css/github-markdown.css';
@import '~highlight.js/styles/github-gist.css';
$color-user: #1F3964;
$transition: 400ms ease-in-out;
.p-operation-area {
  display: flex;
  margin-top: 10px;
  height: calc(100vh - 196px);
}
.p-left-block {
  width: 34%;
  margin-right: 1%;
  background-color: #fff;
}
.p-tab-items {
  display: flex;
  background-color: $color-user;
  border-radius: 8px 8px 0 0;
  padding-inline-start: 0;
}
.p-tab-item {
  background-color: $color-user;
  color: #fff;
  display: block;
  overflow: hidden;
  text-overflow: ellipsis;
  height: 35px;
  line-height: 35px;
  padding: 0 15px;
  cursor: pointer;
  border-right: 1px solid #fff;
  &:hover {
    opacity: 0.7;
    transition: $transition;
    text-decoration: none;
  }
  &:first-child {
    border-radius: 8px 0 0 0;
  }
}
.is-active {
  background-color: #fff;
  color: $color-user;
}
.p-left-block-inner {
  overflow-y: scroll;
  height: calc(100vh - 231px);
  .markdown-body {
    margin-bottom: 15px;
  }
}
.p-tab-content {
  background-color: #fff;
}
.p-block-inner {
  padding: 20px;
}
</style>
