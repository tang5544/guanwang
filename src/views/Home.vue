<template>
  <div class="home" v-loading="loading">
    <swiper id="swiperBox" v-bind:options="swiperOption" ref="mySwiper">
      <swiper-slide class="swiper-slide slide-one">
        <div class="page">
          <h3>保险代理——玉华门店</h3>
          <p>Insurance Agent——YU HUA Store</p>
        </div>
        <p class="slogan">我们提供最全面的保险服务，让您的生活更加安心、无忧。</p>
      </swiper-slide>
      <swiper-slide class="swiper-slide slide-two">
        <div class="page">
          <h3>保险产品</h3>
          <p>Insurance Products</p>
        </div>
        <ul class="case-item">
<!--          <li-->
<!--            v-for="(item,index) in caseList"-->
<!--            :key="index"-->
<!--            v-lazy:background-image="imgserver + news.Img"-->
<!--          >-->
          <li
            v-for="(item,index) in caseList"
            :key="index"
            v-lazy:background-image="require('@/assets'+item.Img)"
          >
            <router-link
              class="text-decoration"
              :to="{path:'/casedetails',query:{Img:item.Img,Title:item.Title,CreateTime:item.CreateTime,Content:item.Content}}"
            >
              <div class="case-item-hover">
                <p class="hover-title">{{item.Title}}</p>
                <div class="bottom"></div>
                <div class="more">
                  <span>MORE</span>
                </div>
              </div>
            </router-link>
          </li>
        </ul>
      </swiper-slide>
      <swiper-slide class="swiper-slide slide-three">
        <div class="page">
          <h3>最新资讯</h3>
          <p>Latest News</p>
        </div>
        <div class="news-content">
          <div class="news-content-item" v-for="(news,i) in newsList" :key="i">
            <div :style="'order: '+ (i%2==0 ? 1: 3)">
              <router-link
                class="text-decoration"
                :to="{path:'/newsdetails',query:{Img:news.Img,Title:news.Title,CreateTime:news.CreateTime,Content:news.Content}}"
              >
                <div class="item-img" v-lazy:background-image="require('@/assets'+news.Img)"></div>
              </router-link>
            </div>
            <div style="order: 2">
              <el-divider>
                <i class="el-icon-apple"></i>
              </el-divider>
            </div>
            <div class="item-content" :style="'order: '+ (i%2==0 ? 3: 1)">
              <h3>{{news.Title}}</h3>
              <p>{{news.Content}}</p>
              <span>{{news.CreateTime}}</span>
            </div>
          </div>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
import { swiper, swiperSlide } from "vue-awesome-swiper";
export default {
  name: "HelloWorld",
  components: {
    swiper,
    swiperSlide
  },
  data() {
    return {
      loading: false,
      caseList: [
        {
          "Id": 29,
          "Img": "/img/products/products1.png",
          "Title": "建设工程完成履约保证保险",
          "Content": "履约保证保险或履约保证险（也称履约责任保险）是指保险公司向履约保证保险的受益人（即投资人）承诺，如果投保人（即债务人，这里专指借款人）不按照合同约定或法律的规定履行义务，则由该保险公司承担赔偿责任的一种保险形式。该险种应用范围已拓展至网贷行业，主要表现为：网贷平台为项目购买履约保险，经保险正式承保的项目，如借款人兑付逾期，保险公司将按照保单约定履行保险责任，投资人的利益将会得到充分保障。\n",
          "Del": null,
          "CreateTime": "2020-06-05T21:12:45.387"
        },
        {
          "Id": 28,
          "Img": "/img/products/products2.png",
          "Title": "旅行社旅游质保金保险",
          "Content": "旅行社质量保证金是指由旅行社缴纳，旅游行政管理部门管理，用于保障旅游者权益的专用款项\n" +
              "1995年，国家旅游局颁布了《旅行社质量保证金暂行规定》和《旅行社质量保证金暂行规定实施细则》。\n" +
              "1996年，国务院颁布了《旅行社管理条例》，调整了我国的旅行社的分类，按照经营的业务范围将旅行社划分为国际旅行社和国内旅行社两大类型。同年，国家旅游局为实施《旅行社管理条例》，发布了《旅行社管理条例实施细则》\n" +
              "随后国家旅游局又发布了《旅行社质量保证金赔偿办法》、《旅行社质量保证金赔偿试行标准》，使该项制度进一步规范和完善，形",
          "Del": null,
          "CreateTime": "2020-06-05T21:05:45.157"
        },
        {
          "Id": 27,
          "Img": "/img/products/products3.png",
          "Title": "建筑工程一切险",
          "Content": "建筑工程一切险是以建筑工程中的材料、装饰物料、设备等为保险标的的保险。保险人承担的主要责任包括： (1) 洪水、地震、暴风雨、山崩、冻灾等自然灾害造成的经济损失；(2) 爆炸、空中飞行物体的坠落、火灾等意外事故造成的经济损失；(3) 盗窃、工人或技术人员缺乏经验、过失、恶意行为所造成的经济损失。",
          "Del": null,
          "CreateTime": "2020-06-05T21:02:05.567"
        },
        {
          "Id": 26,
          "Img": "/img/products/products4.png",
          "Title": "建工意外险（总承包）",
          "Content": "建工意外险（建工意外险）一般指建筑工程施工人员团体人身意外伤害保险",
          "Del": null,
          "CreateTime": "2020-06-05T20:58:05.57"
        },
        {
          "Id": 26,
          "Img": "/img/products/products5.png",
          "Title": "农民工工资保证保险",
          "Content": "农民工工资支付保证保险，是指由保险公司向工程项目所在地建设行政主管部门提供的保证工程项目所在地的施工承包人按规定支付建筑务工人员工资的保险。当施工承包人拖欠务工人员工资导致项目所在地建设行政主管部门及人力资源社会保障部门作出认定或法院文书裁判，由保险公司在保险金额内先行赔付。",
          "Del": null,
          "CreateTime": "2020-06-05T20:58:05.57"
        },
        {
          "Id": 26,
          "Img": "/img/products/products6.png",
          "Title": "非建筑行业安责险",
          "Content": "是指保险机构对投保的生产经营单位发生的生产安全事故造成的人员伤亡和有关经济损失等予以赔偿，并且为投保的生产经营单位提供事故预防服务的商业保险。安全生产责任保险是生产经营单位在发生生产安全事故以后对死亡、伤残者履行赔偿责任的保险，对维护社会安定和谐具有重要作用。对于高危行业分布广泛，伤亡事故时有发生的地区，发展安全生产责任保险，用责任保险等经济手段加强和改善安全生产管理，是强化安全事故风险管控的重要措施，有利于增强安全生产意识，防范事故发生，促进地区安全生产形势稳定好转；有利于预防和化解社会矛盾，减轻各级政",
          "Del": null,
          "CreateTime": "2020-06-05T20:58:05.57"
        },
        {
          "Id": 26,
          "Img": "/img/products/products7.png",
          "Title": "建筑施工安全生产责任险",
          "Content": "是指保险机构对投保的生产经营单位发生的生产安全事故造成的人员伤亡和有关经济损失等予以赔偿，并且为投保的生产经营单位提供事故预防服务的商业保险。安全生产责任保险是生产经营单位在发生生产安全事故以后对死亡、伤残者履行赔偿责任的保险，对维护社会安定和谐具有重要作用。对于高危行业分布广泛，伤亡事故时有发生的地区，发展安全生产责任保险，用责任保险等经济手段加强和改善安全生产管理，是强化安全事故风险管控的重要措施，有利于增强安全生产意识，防范事故发生，促进地区安全生产形势稳定好转；有利于预防和化解社会矛盾，减轻各级政",
          "Del": null,
          "CreateTime": "2020-06-05T20:58:05.57"
        }
      ],
      newsList: [
        {
          "Id": 19,
          "Title": "热烈祝贺玉华门店获取阳光保险代理门店资质",
          "Img": "/img/news/news1.jpg",
          "Type": 1,
          "Content": "热烈祝贺玉华门店获取阳光保险代理门店资质!",
          "CreateTime": "2019-09-4"
        }
        // ,
        // {
        //   "Id": 15,
        //   "Title": "上海科建工程管理有限公司科创板创立大会顺利召开",
        //   "Img": "/img/news/news1.jpg",
        //   "Type": 1,
        //   "Content": "历时2个月的企业经营财务状况梳理及企业内部日常行政运营工作，通过法律法规整合管理，企业各大部门如财务、运营、项目管理、技术研发，都形成了各自的工作流程，各部门相互配合，为科建今后工程管理标准化软件的广泛使用，为成为项目管理行业的佼佼者努力。2018年3月12日上午10时上海科建工程管理股份有限公司创立大会暨2018年第一次临时股东大会顺利召开。",
        //   "CreateTime": "2018-07-23T16:24:11.633"
        // }
      ],
      swiperOption: {
        notNextTick: true, //notNextTick是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
        direction: "vertical", //水平方向移动
        grabCursor: true, //鼠标覆盖Swiper时指针会变成手掌形状，拖动时指针会变成抓手形状
        setWrapperSize: true, //Swiper使用flexbox布局(display: flex)，开启这个设定会在Wrapper上添加等于slides相加的宽或高，在对flexbox布局的支持不是很好的浏览器中可能需要用到。
        autoHeight: true, //自动高度。设置为true时，wrapper和container会随着当前slide的高度而发生变化
        slidesPerView: 1, //设置slider容器能够同时显示的slides数量(carousel模式)。可以设置为数字（可为小数，小数不可loop），或者 'auto'则自动根据slides的宽度来设定数量。loop模式下如果设置为'auto'还需要设置另外一个参数loopedSlides。
        mousewheel: true, //开启鼠标滚轮控制Swiper切换。可设置鼠标选项，默认值false
        mousewheelControl: true, //同上
        height: window.innerHeight - 60, // 高度设置，占满设备高度
        resistanceRatio: 0, //抵抗率。边缘抵抗力的大小比例。值越小抵抗越大越难将slide拖离边缘，0时完全无法拖离。本业务需要
        observeParents: true, //将observe应用于Swiper的父元素。当Swiper的父元素变化时，例如window.resize，Swiper更新

        // 如果自行设计了插件，那么插件的一些配置相关参数，也应该出现在这个对象中，如下debugger
        //debugger: true,

        // swiper的各种回调函数也可以出现在这个对象中，和swiper官方一样
        on: {
          //监听滑动切换事件，返回swiper对象
          // slideChange: () => {
          //   let swiper = this.$refs.mySwiper.swiper;
          //   //console.log(swiper.activeIndex); //滑动打印当前索引
          //   if (swiper.activeIndex === this.list.length - 1) {
          //     //到最后一个加载更多数据
          //     let newList = [];
          //     let listLength = this.list.length;
          //     for (let i = 0; i < 10; i++) {
          //       newList.push(listLength + i);
          //     }
          //     this.list = this.list.concat(newList);
          //   }
          // }
        }
      }
    };
  },
  created() {},
  // 如果你需要得到当前的swiper对象来做一些事情，你可以像下面这样定义一个方法属性来获取当前的swiper对象，同时notNextTick必须为true
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper;
    }
  },
  // mounted() {
  //   this.$http
  //     .all([
  //       this.$http.get("Cases/GetCasesAll"),
  //       this.$http.get(`News?type=1&num=3`)
  //     ])
  //     .then(
  //       this.$http.spread((responseCases, responseNews) => {
  //         this.caseList = responseCases.data;
  //         this.newsList = responseNews.data;
  //         this.loading = false;
  //       })
  //     );
  // }
};
</script>

<style lang="scss" scoped>
/* .el-header {
  position: absolute;
} */
.swiper-slide {
  font-size: 24px;
  // text-align: center;
  // line-height: 100px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;

  .page {
    text-align: center;
    height: 100px;
    overflow: hidden;
    h3,
    p {
      font-size: 40px;
      font-weight: 400;
      color: #fff;
    }
  }

  .slogan {
    text-align: center;
    font-size: 50px;
    color: #fff;
    padding: 30px 0;
  }
}
//经典案例
.case-item {
  width: 1400px;
  //height: 500px;
  overflow: hidden;
  margin: 0 auto;
  margin-top: 30px;
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  li {
    width: 450px;
    height: 300px;
    list-style: none;
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
    background-origin: content-box;
    margin: 5px;
    position: relative;
    overflow: hidden;

    &:hover {
      .case-item-hover {
        opacity: 1;
        transition: all 0.4s ease-in-out;
      }
    }
  }
}
//经典案例hover
.case-item-hover {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
  overflow: hidden;
  background-color: rgba(225, 56, 52, 0.7);

  .hover-title {
    height: 50px;
    color: #fff;
    font-size: 18px;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    font-weight: 400;
    margin-top: 20px;
  }
  .bottom {
    border-bottom: 1px solid #fff;
    width: 60px;
    margin: 0 auto;
  }
  .more {
    width: 90px;
    padding: 5px 5px;
    margin: 0 auto;
    margin-top: 100px;
    border: 2px solid #fff;
    span {
      color: #fff;
      font-size: 20px;
    }
  }
}
// .swiper-slide:nth-child(2n) {
//   background: skyblue;
// }
// .swiper-slide:nth-child(2n-1) {
//   background: seashell;
// }
.slide-one {
  background: url(../assets/img/home_top1.jpg) no-repeat center;
  background-size: cover;
}
.slide-two {
  background: url(../assets/img/home_do.jpg) no-repeat center;
  background-size: cover;
}
.slide-three {
  background: url(../assets/img/home_anli.jpg) no-repeat center;
  background-size: cover;
}
//最新资讯
.news-content {
  width: 1240px;
  margin: 0 auto;
  margin-top: 40px;
  display: flex;
  justify-content: center;

  &-item {
    width: 400px;
    display: flex;
    flex-direction: column;

    .item-img {
      width: 360px;
      height: 230px;
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
      background-origin: content-box;
      margin: 0 auto;
    }
    .el-divider {
      background-color: #fff;
      height: 3px;
      .el-divider__text {
        width: 20px;
        height: 20px;
        border-radius: 50%;
        padding: 0px;
        color: #fff;
      }
    }
    .item-content {
      width: 360px;
      height: 230px;
      margin: 0 auto;
      //border: 1px solid paleturquoise;
      h3 {
        font-size: 22px;
        height: 30px;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      p {
        font-size: 15px;
        height: 80px;
        overflow: hidden;
        margin: 10px 0;
        text-overflow: ellipsis;
        display: -webkit-box;
        -webkit-line-clamp: 4;
        -webkit-box-orient: vertical;
        white-space: normal !important;
        word-wrap: break-word;
      }
      span {
        display: block;
        font-size: 14px;
        text-align: end;
      }
      h3,
      p,
      span {
        color: #fff;
      }
    }
  }
}
.order {
  order: -1;
}
.order-img {
  order: 1;
}
</style>
