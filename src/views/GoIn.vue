<template>
  <div class="go-in">
    <banner img="../assets/img/bgtop.jpg" title="关于我们" />
    <div class="section" v-loading="loading">
      <div class="section-content">
        <div class="content-summary">
          <div class="summary-left">
            <p class="title">公司简介</p>
            <p class="eTitle">ABOUT US</p>
            <div class="content">
              <h1>我们是谁</h1>
              <p>我们是一家专注于提供高品质保险服务的公司。我们的目标是帮助客户保护自己和他们所关心的人，为他们提供安心和保障。</p>
              <h1>我们的团队</h1>
              <p>我们的团队由一群经验丰富的保险专家组成。他们致力于为客户提供最优质的保险服务，包括保险咨询、理赔等方面。</p>
              <h1>联系我们</h1>
              <p>如有任何问题或咨询，请随时联系我们。我们的客服人员会尽快回复您。</p>
              <p>联系人：唐先生</p>
              <p>电话：13556718254</p>
              <p>邮箱：504801283@qq.com</p>
              <p>地址：广东省东莞市莞城街道高峰楼阳光保险玉华门店</p>
            </div>
          </div>
          <div class="summary-right">
            <img src="../assets/img/jianjietopmin.jpg" alt />
          </div>
        </div>
        <el-divider class="el-divider-active">
          <i class="el-icon-arrow-down el-icon-arrow-down-active"></i>
        </el-divider>
        <!-- 发展历程 -->
        <div class="content-course">
          <div class="top">
            <h3>发展历程</h3>
            <p>DEVELOPMENT</p>
            <div class="border"></div>
            <div class="timeline"></div>
          </div>
          <div class="course-time">
            <swiper :options="swiperOption" ref="mySwiper">
              <swiper-slide v-for="(item,index) in courseList" :key="index">
                <div class="time-show">
                  <div class="time-show-item" v-for="(courseOne,one) in item" :key="one">
                    <div class="item-top" :class="{'order-top' : one%2===1}"></div>
                    <el-divider>
                      <i class="el-icon-mobile-phone"></i>
                    </el-divider>
                    <div class="item-bottom" :class="{'order' : one%2===1}">
                      <div class="item-bottom-content">
                        <p>{{courseOne.Content}}</p>
                        <p>{{courseOne.Year}}</p>
                      </div>
                    </div>
                  </div>
                </div>
              </swiper-slide>
              <div class="swiper-button-prev" slot="button-prev"></div>
              <div class="swiper-button-next" slot="button-next"></div>
            </swiper>
          </div>
        </div>

        <div class="content-culture">
          <h3>企业文化</h3>
          <h3>CULTURE</h3>
          <p>我们只专注一件事情——生命财产保险安全</p>
          <span>以客户为中心：保险公司的核心业务是为客户提供保险服务，因此以客户为中心是保险公司的重要价值观。保险公司会注重客户需求，提供优质的服务，建立长期的客户关系</span>
          <span>诚信和透明：保险公司需要建立信任，因此诚信和透明是企业文化中的重要价值观。保险公司会遵守法律法规，公开透明地向客户提供信息，保证客户的权益</span>
          <span>创新和进取：保险市场竞争激烈，保险公司需要不断创新和进取，提高服务质量和效率，满足客户需求。因此，创新和进取是保险公司企业文化中的重要价值观</span>
          <span>社会责任：保险公司需要承担社会责任，为社会做出贡献。因此，社会责任是保险公司企业文化中的重要价值观。保险公司会积极参与公益活动，为社会做出贡献。</span>
        </div>
        <!-- 公司荣誉 -->
        <div class="content-honor">
          <div class="honor-big-img">
            <el-dialog :title="dialogTitle" :visible.sync="dialogTableVisible">
              <img v-lazy="dialogUrl" alt />
            </el-dialog>
          </div>
          <div class="top">
            <h3>公司荣誉</h3>
            <p>HONOR</p>
            <div class="border"></div>
          </div>
          <ul class="honor-show">
            <li v-for="(honor,index) in honorList" :key="index">
              <img
                  v-lazy:background-image="require('@/assets'+honor.Img)"
                @click="dialogTableVisible = true ;dialogUrl = require('@/assets'+honor.Img);dialogTitle= honor.Remark"
              />
            </li>
          </ul>
          <p>点击图片查看大图</p>
        </div>
        <!-- 团队风采 -->
        <div class="content-team">
          <div class="top">
            <h3>团队风采</h3>
            <p>TEAM</p>
          </div>
          <el-carousel :interval="4000" type="card">
            <el-carousel-item v-for="(team,index) in teamItem" :key="index">
              <div class="swiper-img" v-lazy:background-image="require('@/assets'+team.Img)"></div>
            </el-carousel-item>
          </el-carousel>
        </div>
        <!-- 合作伙伴 -->
        <div class="content-partner">
          <div class="top">
            <h3>合作伙伴</h3>
            <p>RARTNERS</p>
            <ul class="partner-img">
              <li v-for="(partner,i) in partnerImg" :key="i">
                <img v-lazy:background-image="require('@/assets'+partner.Img)" alt />
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from "../components/Banner";
import { swiper, swiperSlide } from "vue-awesome-swiper";
export default {
  components: {
    Banner,
    swiper,
    swiperSlide
  },
  data() {
    return {
      loading: false,
      honorList: [{
        CreateTime: "2019-09-4",
        Id: 31,
        Img: "/img/news/news1.jpg",
        Remark: "玉华门店获取阳光保险代理门店资质"
      }],
      partnerImg: [{
        CreateTime: "2021-08-10T01:59:55.71",
        Id: 25,
        Img: "/img/news/news1.jpg",
        Remark: "丰丰"
      }],
      courseList:[],
      courseList2: [
          {
            "Id":10,
            "Year":"2019年9月",
            "Content":"东莞市东城街道阳光财产保险玉华专属代理店成立"
          }],
      teamItem: [{
        CreateTime: "2020-06-05T21:34:46.743",
        Id: 16,
        Img: "/img/news/news1.jpg",
        Remark: "参加第七届中国（上海）国际技术进出口交易会"
      }],
      swiperOption: {
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev"
        }
      },
      dialogTableVisible: false,
      dialogUrl: "",
      dialogTitle: ""
    };
  },
  mounted() {

    var groupCount = Math.ceil(this.courseList2.length / 2);
    window.console.log("SS");
            window.console.log(groupCount);
            for (let i = 0; i < groupCount; i++) {
              let img2 = [];
              for (let j = 0; j < 2; j++) {
                if (this.courseList2.length - 1 >= i * 2 + j) {
                  img2.push(this.courseList2[i * 2 + j]);
                }
              }
              window.console.log("img2");
              window.console.log(img2);
              this.courseList.push(img2);
            }
    window.console.log(this.courseList);
    // this.$http
    //   .all([
    //     this.$http.get("Honor/GetHonorAll"),
    //     this.$http.get("Enterprise/GetEnterpriseAll"),
    //     this.$http.get(`Team/GetTeamAll`),
    //     this.$http.get(`Course/GetCourseAll`)
    //   ])
    //   .then(
    //     this.$http.spread(
    //       (responseHonor, responseEnterprise, responseTeam, responseCourse) => {
    //         this.honorList = responseHonor.data;
    //         this.partnerImg = responseEnterprise.data;
    //         this.teamItem = responseTeam.data;
    //
    //         var groupCount = Math.ceil(responseCourse.data.length / 2);
    //         window.console.log(groupCount);
    //         for (let i = 0; i < groupCount; i++) {
    //           let img2 = [];
    //           for (let j = 0; j < 2; j++) {
    //             if (responseCourse.data.length - 1 >= i * 2 + j) {
    //               img2.push(responseCourse.data[i * 2 + j]);
    //             }
    //           }
    //           this.courseList.push(img2);
    //         }
    //         window.console.log(this.courseList);
    //         this.loading = false;
    //       }
    //     )
    //   );
  }
};
</script>

<style lang="scss" scoped>
* {
  margin: 0;
  padding: 0;
}

.go-in {
  width: 100%;
  height: 100%;
  background-color: #14679f;
  position: relative;
  overflow: hidden;
  .section {
    width: 100%;
    &-content {
      width: 1240px;
      margin: 0 auto;
      background-color: #fff;

      .content-summary {
        //height: 500px;
        display: flex;
        justify-content: space-around;
        padding: 100px 0;
        .summary-left {
          width: 600px;
          .title {
            font-size: 25px;
            color: #e13834;
          }
          .eTitle {
            font-size: 17px;
            color: #e13834;
            padding: 20px 0;
          }
          .content {
            color: #14679f;
            font-size: 14px;
            text-indent: 25px;
            line-height: 30px;
          }
        }

        .summary-right {
          width: 400px;
          height: 310px;
          border: 2px solid #1d42b9;
          //animation: imgboxkey 4s infinite;
          border-radius: 10px;
          margin-top: 80px;
          text-align: center;

          img {
            width: 360px;
            height: 270px;
            margin-top: 20px;
            //animation: imgbo 4s infinite;
          }
        }
      }

      //发展历程
      .content-course {
        padding: 50px 0;
        .course-time {
          width: 1000px;
          height: 400px;
          margin: 20px auto;
          .swiper-container {
            height: 100%;
          }
          .time-show {
            width: 700px;
            height: 100%;
            margin: 0 auto;
            display: flex;
            .time-show-item {
              width: 350px;
              height: 100%;
              overflow: hidden;
              display: flex;
              flex-direction: column;

              .item-top,
              .item-bottom {
                height: 190px;
              }
              .item-bottom {
                // display: flex;
                // align-content: center;
                .item-bottom-content {
                  background-color: #1667a0;
                  margin: 20px 0;
                  p {
                    color: #fff;
                    text-align: center;
                    padding: 15px;
                  }
                }
              }
            }
          }
        }
      }

      //企业文化
      .content-culture {
        height: 450px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        padding-left: 100px;
        background-color: #c2daeb;
        h3 {
          color: #3c6088;
          font-size: 26px;
        }
        p {
          color: #3c6088;
          font-size: 26px;
          padding: 5px 0;
        }
        span {
          font-weight: 400;
          line-height: 36px;
          font-size: 18px;
          padding: 5px 0;
        }
      }

      //公司荣誉
      .content-honor {
        padding: 50px 0;
        .honor-show {
          width: 1000px;
          margin: 30px auto;
          display: flex;
          flex-wrap: wrap;
          justify-content: flex-start;
          align-content: flex-start;

          li {
            width: 220px;
            height: 320px;
            margin-left: 15px;
            list-style: none;
            border: 1px solid palegoldenrod;

            img {
              width: 100%;
              height: 100%;
            }
          }
        }
        p {
          text-align: center;
          color: #3c6088;
        }
      }

      //团队风采
      .content-team {
        padding: 50px 100px;
        .swiper-img {
          height: 400px;
          background: no-repeat center;
          background-size: cover;
        }
      }

      //合作伙伴
      .content-partner {
        padding: 50px 0;
        .partner-img {
          width: 950px;
          margin: 20px auto;
          display: flex;
          justify-content: flex-start;
          flex-wrap: wrap;
          li {
            width: 107px;
            height: 107px;
            list-style: none;
            margin: 10px 25px;

            img {
              width: 100%;
              height: 100%;
              border: 1px solid rgb(194, 218, 235);
            }
          }
        }
      }
    }
  }
}

@keyframes imgboxkey {
  0% {
    border: solid rgb(29, 66, 185) 2px;
  }
  40% {
    border: solid rgb(255, 255, 255) 2px;
  }
  60% {
    border: solid rgb(255, 255, 255) 2px;
  }
  100% {
    border: solid rgb(29, 66, 185) 2px;
  }
}

@keyframes imgbo {
  0% {
    transform: scale(1);
    box-shadow: 0px 0px 0px 0px #ababab;
  }
  50% {
    transform: scale(1.1);
    box-shadow: 0px 0px 10px 5px #ababab;
  }
  100% {
    transform: scale(1);
    box-shadow: 0px 0px 0px 0px #ababab;
  }
}
.el-divider--horizontal {
  margin: 1px 0;
}

.top {
  h3,
  p {
    text-align: center;
    color: #3c6088;
    font-weight: 400;
    padding: 10px 0;
  }
  h3 {
    font-size: 30px;
  }
  p {
    font-size: 20px;
  }
  .border {
    border-bottom: 1px solid #3c6088;
    width: 15%;
    margin: 0 auto;
  }
}
// .swiper-button-disabled {
//   display: none;
// }
.order {
  order: -1;
}
.order-top {
  order: 1;
}
.el-divider {
  background-color: red;
  height: 3px;
  .el-divider__text {
    width: 20px;
    height: 20px;
    border-radius: 50%;
    padding: 0px;
    color: #fff;
    border: 3px solid red;
  }
}
.el-divider-active {
  background-color: #3c6088;
}
.honor-big-img {
  width: 100%;
  height: 100%;
  z-index: 10;
  text-align: center;
  padding-bottom: 20px;
  padding: 5%;
  //background-color: #14679f;
  .el-dialog__wrapper {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    overflow: auto;
    margin: 0;

    .el-dialog__body {
      overflow: hidden;
      img {
        width: 100%;
      }
    }
  }
}
</style>