<template>
  <div class="case">
    <banner img="../assets/img/bgtop.jpg" title="保险产品" />
    <div class="case-section" v-loading="loading">
      <div class="case-section-content">
        <div class="case-section-content-list" v-for="(cas,index) in caseList" :key="index">
          <img v-lazy:background-image="require('@/assets'+cas.Img)" />
          <div class="content-list-abstract" :class="{'abstract-active' : index%2!=1}">
            <p class="abstract-title">{{cas.Title}}</p>
            <p class="abstract-content">{{cas.Content}}</p>
            <div class="more">
              <router-link
                class="text-decoration"
                :to="{path:'/casedetails',query:{Img:cas.Img,Title:cas.Title,CreateTime:cas.CreateTime,Content:cas.Content}}"
              >
                <span>more</span>
                <img src="../assets/img/sanjiao.png" />
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Banner from "../components/Banner";
export default {
  components: {
    Banner
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
    };
  },
  mounted() {
    // window.console.log("case");
    // this.$http
    //   .get("Cases/GetCasesAll")
    //   .then(response => {
    //     //console.log(response);
    //     this.caseList = response.data;
    //     //window.console.log(this.caseList);
    //     this.loading = false;
    //   })
    //   .catch(function(error) {
    //     window.console.log(error);
    //   });
  }
};
</script>

 <style lang="scss" scoped>
.case {
  width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  background-color: #14679f;

  &-section {
    width: 100%;
    &-content {
      width: 1240px;
      min-height: 1000px;
      margin: 0 auto;
      background-color: #fff;

      &-list {
        width: 100%;
        height: 500px;
        display: flex;
        justify-content: center;
        align-items: center;
        border: 1px solid pink;

        img {
          width: 612px;
          height: 314px;
        }
        .content-list-abstract {
          width: 290px;
          height: 350px;
          padding: 0 20px;
          display: flex;
          flex-direction: column;
          justify-content: space-around;
          .abstract-title {
            line-height: 30px;
            font-size: 22px;
            color: #e13834;
          }
          .abstract-content {
            height: 150px;
            color: #484848;
            font-size: 15px;

            overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 7;
            -webkit-box-orient: vertical;
            white-space: normal !important;
            word-wrap: break-word;
            //border: 1px solid pink;
          }
          .more {
            display: flex;
            justify-content: flex-start;
            .text-decoration {
              text-decoration: none;

              span {
                color: #000;
              }
              img {
                width: 12px;
                height: 12px;
              }
            }
          }
        }
        .abstract-active {
          order: -1;
        }
      }
    }
  }
}
</style>