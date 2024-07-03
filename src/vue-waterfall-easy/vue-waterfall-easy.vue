<!-- —————————————↓SCSS———————分界线————————————————————————— -->
<style lang="scss" scoped>
.vue-waterfall-easy-container {
  width: 100%;
  height: 100%;
  position: relative;
  .vue-waterfall-easy-scroll {
    position: relative;
    width: 100%;
    height: 100%;
    overflow-x: hidden;
    overflow-y: scroll;
    -webkit-overflow-scrolling: touch;
  }
  .vue-waterfall-easy {
    position: absolute;
    width: 100%; // 移动端生效
    @keyframes show-card {
      0% {
        transform: scale(0.5);
      }
      100% {
        transform: scale(1);
      }
    }
    & > .img-box {
      position: absolute;
      box-sizing: border-box;
      width: 50%; // 移动端生效
    }
    & > .img-box.default-card-animation {
      animation: show-card 0.4s;
      transition: left 0.6s, top 0.6s;
      transition-delay: 0.1s;
    }
    a {
      display: block;
    }
    a.img-inner-box {
      box-shadow: 0 1px 3px rgba(0, 0, 0, 0.3);
      border-radius: 4px;
    }
    .__err__ .img-wraper {
      background-image: url(data:image/png;base64,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);
      background-repeat: no-repeat;
      background-position: center;
      background-size: 50px;
      background-color: #EBF4FF; 
      box-shadow: 0px 2px 50px 0px rgba(10,12,14,0.2);
      img {
        display: none;
      }
    }
    a.img-wraper {
      & > img {
        width: 100%;
        display: block;
        border: none;
      }
    }
    .over {
      position: absolute;
      width: 100%;
      text-align: center;
      font-size: 12px;
      line-height: 1.6;
      color: #aaa;
    }
  }

  & > .loading.first {
    bottom: 50%;
    transform: translate(-50%, 50%);
  }
  & > .loading {
    position: absolute;
    left: 50%;
    transform: translateX(-50%);
    bottom: 6px;
    z-index: 999;
    @keyframes ball-beat {
      50% {
        opacity: 0.2;
        transform: scale(0.75);
      }
      100% {
        opacity: 1;
        transform: scale(1);
      }
    }

    &.ball-beat > .dot {
      vertical-align: bottom;
      background-color: #4b15ab;
      width: 12px;
      height: 12px;
      border-radius: 50%;
      margin: 3px;
      animation-fill-mode: both;
      display: inline-block;
      animation: ball-beat 0.7s 0s infinite linear;
    }
    &.ball-beat > .dot:nth-child(2n-1) {
      animation-delay: 0.35s;
    }
  }
}
</style>

<!-- —————————————↓HTML————————分界线———————————————————————— -->
<template lang="pug">
.vue-waterfall-easy-container(:style="{width: width&&!isMobile ? width+'px' : '', height: parseFloat(height)==height ? height+'px': height }")
  .loading.ball-beat(v-show="isPreloading_c", :class="{first:isFirstLoad}")
    slot(name="loading", :isFirstLoad="isFirstLoad")
    .dot(v-if="!hasLoadingSlot", v-for="n in loadingDotCount",:style="loadingDotStyle")
  //- 为了防止loading 跟随滚动
  .vue-waterfall-easy-scroll(ref="scrollEl")
    slot(name="waterfall-head")
    .vue-waterfall-easy(:style="isMobile? '' :{width: colWidth*cols+'px',left:'50%', marginLeft: -1*colWidth*cols/2 +'px'}")
      .img-box(
        v-for="(v,i) in imgsArr_c",
        :class="[cardAnimationClass, {__err__: v._error}]"
        :style="{padding: (isMobile ? mobileGap : gap)/2+'px', width: isMobile ? '' : colWidth+'px'}"
      )
        component.img-inner-box(
          :is="isRouterLink  && linkRange=='card' ? 'router-link' : 'alink'",
          :data-index="i",
          :to="linkRange=='card' ? v[hrefKey] : false")
          component.img-wraper(
            v-if="v[srcKey]",
            :is="isRouterLink && linkRange=='img' ? 'router-link' :'alink'",
            :to="linkRange=='img' ? v[hrefKey] : false ",
            :style="{width:imgWidth_c + 'px',height:v._height ? v._height+'px':false}")
            img(:src="v[srcKey]")
          slot(:index="i",:value="v")
      .over(v-if="over",ref="over")
        slot(name="waterfall-over") 被你看光了
</template>

<!-- ——————————————↓JS—————————分界线———————————————————————— -->
<script>
import alink from './components/alink.vue'

export default {
  name: 'vue-waterfall-easy',
  components: {
    alink
  },
  props: {
    width: { // 容器宽度
      type: Number
    },
    height: { // 容器高度
      type: [Number, String]
    },
    reachBottomDistance: { // 滚动触底距离，触发加载新图片
      type: Number, // selector
      default: 20  // 默认在最低那一列到底时触发
    },
    loadingDotCount: { // loading 点数
      type: Number,
      default: 3
    },
    loadingDotStyle: {
      type: Object,
    },
    gap: { // .img-box 间距
      type: Number,
      default: 20
    },
    mobileGap: {
      type: Number,
      default: 8
    },
    maxCols: {
      type: Number,
      default: 5
    },
    imgsArr: {
      type: Array,
      required: true,
    },
    srcKey: {
      type: String,
      default: 'src'
    },
    hrefKey: {
      type: String,
      default: 'href'
    },
    imgWidth: {
      type: Number,
      default: 240
    },
    isRouterLink: {
      type: Boolean,
      default: false
    },
    linkRange: { // card | img | custom 自定义通过slot自定义链接范围
      type: String,
      default: 'card'
    },
    loadingTimeOut: { // 预加载事件小于500毫秒就不显示加载动画，增加用户体验
      type: Number,
      default: 500
    },
    cardAnimationClass: {
      type: [String],
      default: 'default-card-animation'
    },
    enablePullDownEvent: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      msg: 'this is from vue-waterfall-easy.vue',
      isMobile: !!navigator.userAgent.match(/(iPhone|iPod|Android|ios)/i), // 初始化移动端
      isPreloading: true, // 正在预加载中，显示加载动画
      isPreloading_c: true,
      imgsArr_c: [], // 待图片预加载imgsArr完成，插入新的字段height之后,才会生成imgsArr_c，这时才开始渲染
      loadedCount: 0,
      cols: NaN, // 需要根据窗口宽度初始化
      imgBoxEls: null, // 所有的.img-box元素
      beginIndex: 0, // 开始要排列的图片索引,首次为第二列的第一张图片，后续加载则为已经排列图片的下一个索引
      colsHeightArr: [],
      // 自定义loading
      LoadingTimer: null,
      isFirstLoad: true, // 首次加载
      over: false, // 结束waterfall加载
    }
  },
  computed: {
    colWidth() { // 每一列的宽度
      return this.imgWidth + this.gap
    },
    imgWidth_c() { // 对于移动端重新计算图片宽度`
      return this.isMobile ? window.innerWidth / 2 - this.mobileGap : this.imgWidth
    },
    hasLoadingSlot() {
      return !!this.$scopedSlots.loading
    }
  },
  mounted() {
    this.bindClickEvent()
    this.loadingMiddle()

    this.preload()
    this.cols = this.calcuCols()
    this.$on('preloaded', () => {
      this.isFirstLoad = false

      this.imgsArr_c = this.imgsArr.concat([]) // 预加载完成，这时才开始渲染
      this.$nextTick(() => {
        this.isPreloading = false
        this.imgBoxEls = this.$el.getElementsByClassName('img-box')
        // console.log('图片总数', this.imgBoxEls.length)
        this.waterfall()
      })

    })
    if (!this.isMobile && !this.width) window.addEventListener('resize', this.response)
    if (this.isMobile && this.enablePullDownEvent) this.pullDown()
    this.scroll()
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.response)
  },
  watch: {
    isPreloading(newV, oldV) {
      if (newV) {
        setTimeout(() => {
          if (!this.isPreloading) return // 500毫秒内预加载完图片则不显示加载动画
          this.isPreloading_c = true
        }, this.loadingTimeOut)
      } else {
        this.isPreloading_c = false
      }
    },
    imgsArr(newV, oldV) {
      if (this.imgsArr_c.length > newV.length || (this.imgsArr_c.length > 0 && newV[0] && !newV[0]._height)) {
        // console.log('reset')
        this.reset()
      }
      this.preload()
    },

  },
  methods: {
    // ==1== 预加载
    preload(src, imgIndex) {
      this.imgsArr.forEach((imgItem, imgIndex) => {
        if (imgIndex < this.loadedCount) return // 只对新加载图片进行预加载
        // 无图时
        if (!imgItem[this.srcKey]) {
          this.imgsArr[imgIndex]._height = '0'
          this.loadedCount++

          // 支持无图模式
          if (this.loadedCount == this.imgsArr.length) {
            this.$emit('preloaded')
          }
          return
        }

        var oImg = new Image()
        oImg.src = imgItem[this.srcKey]
        oImg.onload = oImg.onerror = (e) => {

          this.loadedCount++
          // 预加载图片，计算图片容器的高
          this.imgsArr[imgIndex]._height = e.type == 'load' ? Math.round(this.imgWidth_c / (oImg.width / oImg.height)) : (this.isMobile ? this.imgWidth_c : this.imgWidth)
          if (e.type == 'error') {
            this.imgsArr[imgIndex]._error = true
            this.$emit('imgError', this.imgsArr[imgIndex])
          }

          if (this.loadedCount == this.imgsArr.length) {
            this.$emit('preloaded')
          }
        }
      })

    },
    // ==2== 计算cols
    calcuCols() { // 列数初始化
      var waterfallWidth = this.width ? this.width : window.innerWidth
      var cols = parseInt(waterfallWidth / this.colWidth)
      cols = cols === 0 ? 1 : cols
      return this.isMobile
        ? 2
        : (cols > this.maxCols ? this.maxCols : cols)
    },
    // ==3== waterfall布局
    waterfall() {
      if (!this.imgBoxEls) return
      // console.log('waterfall')
      var top, left, height, colWidth = this.isMobile ? this.imgBoxEls[0].offsetWidth : this.colWidth
      if (this.beginIndex == 0) this.colsHeightArr = []
      for (var i = this.beginIndex; i < this.imgsArr.length; i++) {
        if (!this.imgBoxEls[i]) return
        height = this.imgBoxEls[i].offsetHeight
        if (i < this.cols) {
          this.colsHeightArr.push(height)
          top = 0
          left = i * colWidth
        } else {
          var minHeight = Math.min.apply(null, this.colsHeightArr) // 最低高低
          var minIndex = this.colsHeightArr.indexOf(minHeight) // 最低高度的索引
          top = minHeight
          left = minIndex * colWidth
          // 设置元素定位的位置
          // 更新colsHeightArr
          this.colsHeightArr[minIndex] = minHeight + height
        }

        this.imgBoxEls[i].style.left = left + 'px'
        this.imgBoxEls[i].style.top = top + 'px'
      }

      this.beginIndex = this.imgsArr.length // 排列完之后，新增图片从这个索引开始预加载图片和排列

    },

    // ==4== resize 响应式
    response() {
      var old = this.cols
      this.cols = this.calcuCols()
      if (old === this.cols) return // 列数不变直接退出
      this.beginIndex = 0 // 开始排列的元素索引
      this.waterfall()
      if (this.over) this.setOverTipPos()
    },

    // ==5== 滚动触底事件
    scrollFn() {
      var scrollEl = this.$refs.scrollEl
      if (this.isPreloading) return
      var minHeight = Math.min.apply(null, this.colsHeightArr)
      if (scrollEl.scrollTop + scrollEl.offsetHeight > minHeight - this.reachBottomDistance) {
        this.isPreloading = true
        // console.log('scrollReachBottom')
        this.$emit('scrollReachBottom') // 滚动触底
      }
    },
    scroll() {
      this.$refs.scrollEl.addEventListener('scroll', this.scrollFn)
    },
    waterfallOver() {
      this.$refs.scrollEl.removeEventListener('scroll', this.scrollFn)
      this.isPreloading = false
      this.over = true
      this.setOverTipPos()
    },
    setOverTipPos() {
      var maxHeight = Math.max.apply(null, this.colsHeightArr)
      this.$nextTick(() => {
        this.$refs.over.style.top = maxHeight + 'px'
      })
    },
    // ==6== 点击事件绑定
    bindClickEvent() {
      this.$el.querySelector(".vue-waterfall-easy")
        .addEventListener('click', e => {
          var targetEl = e.target;
          if (e.target.className.indexOf('over') !== -1) return
          if (targetEl.className.indexOf("img-box") != -1) return
          while (targetEl.className.indexOf("img-inner-box") == -1) {
            targetEl = targetEl.parentNode;
          }
          var index = targetEl.getAttribute("data-index");
          this.$emit('click', e, {
            index,
            value: this.imgsArr_c[index],
          })
        })
    },
    // ==7== 下拉事件
    pullDown() {
      var scrollEl = this.$el.querySelector('.vue-waterfall-easy-scroll')
      var startY
      scrollEl.addEventListener('touchmove', (e) => {

        if (scrollEl.scrollTop === 0) {
          var t = e.changedTouches[0]
          if (!startY) startY = t.pageY
          var pullDownDistance = t.pageY - startY
          if (pullDownDistance > 0) {
            e.preventDefault()
          }
          this.$emit('pullDownMove', pullDownDistance)
        }
      })
      scrollEl.addEventListener('touchend', (e) => {
        if (scrollEl.scrollTop === 0) {
          startY = NaN
          this.$emit('pullDownEnd')
        }
      })

    },
    // other
    loadingMiddle() {
      // 对滚动条宽度造成的不居中进行校正
      var scrollEl = this.$el.querySelector('.vue-waterfall-easy-scroll')
      var scrollbarWidth = scrollEl.offsetWidth - scrollEl.clientWidth
      this.$el.querySelector('.loading').style.marginLeft = -scrollbarWidth / 2 + 'px'
    },
    reset() {
      this.imgsArr_c = []
      this.beginIndex = 0
      this.loadedCount = 0
      this.isFirstLoad = true
      this.isPreloading = true
      this.scroll()
      this.over = false
    }
  }
}
</script>
