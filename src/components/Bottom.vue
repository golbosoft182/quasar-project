<template>
  <div class="cstm-bottom">
    <div class="cstm-container">
        <div class="inner-container">
            <div class="row">
              <div class="col-12 col-md-4">
                  <div class="bottom-info">
                    <div class="logo-bottom">
                      <img :src="logoSrcBottom" alt="Logo" title="Logo" style="height: 34px; width: 187px">
                    </div>
                    <div class="tagline">
                      우리는 국가의 장벽을 넘어 최고의 인재를 매<br/>칭해드립니다.
                    </div>
                    <div class="phone">
                      <a href="tel:010-0000-0000">010-0000-0000</a>
                    </div>
                    <div class="email">
                      <a href="mailto:aaaaa@naver.com">aaaaa@naver.com</a>
                    </div>
                  </div>
              </div>
              <div class="col-12 col-md-8">
                <div class="row">
                  <div class="col-6 col-md-3" v-for="(item, index) in jsonData" :key="index">
                    <div class="tile-info">
                      <div class="inner-tile">
                        <div class="img-info">
                          <a :href="item.urlLink"><q-img
                            :src="item.imgSrc"
                            loading="lazy"
                            spinner-color="white"
                            height="40px"
                            style="width: 40px"
                          /></a>
                        </div>
                        <div class="tile-headline">
                          <a :href="item.urlLink">{{ item.headline }}</a>
                        </div>
                        <div class="tile-link">
                          <a :href="item.urlLink">{{ item.link }}</a>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="row cstm-row-bottom">
              <div class="col-12 col-md-4">
                  <div class="row">
                      <div class="col-6 col-md-6">
                          <div class="widget-wrapper">
                            <div class="widget-info-head">
                              상호명
                            </div>
                            <div class="widget-body">
                              하이퍼하이어
                            </div>
                            <div class="widget-bottom">
                              Hyperhire India Private Limited
                            </div>
                          </div>
                      </div>
                      <div class="col-6 col-md-6">
                        <div class="widget-wrapper">
                            <div class="widget-info-head">
                              대표 CEO
                            </div>
                            <div class="widget-body">
                              김주현
                            </div>
                            <div class="widget-bottom">
                              Juhyun Kim
                            </div>
                          </div>
                      </div>
                  </div>
              </div>
              <div class="col-12 col-md-8">
                      <div class="row">
                          <div class="col-6 col-md-3">
                            <div class="widget-wrapper">
                              <div class="widget-info-head">
                                사업자등록번호 CIN
                              </div>
                              <div class="widget-body">
                                <a href="tel:4278601187">427-86-01187</a>
                              </div>
                              <div class="widget-bottom">
                                U74110DL2016PTC290812 
                              </div>
                            </div>
                          </div>
                          <div class="col-6 col-md-9">
                            <div class="widget-wrapper">
                              <div class="widget-info-head">
                                주소 ADDRESS
                              </div>
                              <div class="widget-body">
                                서울특별시 강남대로 479, 지하 1층 238호 
                              </div>
                              <div class="widget-bottom">
                                <a href="https://maps.app.goo.gl/EKPEgPYc3PpVfHaXA" target="_blank">D-138, Street number 11, Jagjeet Nagar, North East Delhi, New Delhi, 
110053 India</a>
                              </div>
                            </div>  
                          </div>         
                      </div>
              </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
// Import the logo image bottom
import logoSrcBottom from 'assets/images/logo-bottom.svg';

export default {
  name: 'CstmBottom',
  data() {
    return {
      jsonData: [
        {
          imgSrc: 'images/cstm-tag-ico.svg',
          headline: '해외 개발자 원격 채용',
          link: '바로가기',
          urlLink: 'javascript:;',
        },
        {
          imgSrc: 'images/cstm-people-ico.svg',
          headline: '외국인 원격 채용 (비개발)',
          link: '바로가기',
          urlLink: 'javascript:;',
        },
        {
          imgSrc: 'images/cstm-kor-ico.svg',
          headline: '한국어 가능 외국인 채용',
          link: '바로가기',
          urlLink: 'javascript:;',
        },
        {
          imgSrc: 'images/cstm-set-ico.svg',
          headline: '해외 개발자 활용 서비스',
          link: '바로가기',
          urlLink: 'javascript:;',
        },
        // Add more items as needed
      ]
    };
  },
  setup () {
    return {
      logoSrcBottom: logoSrcBottom
    }
  }
}
</script>
