<template>
  <div class="animation">
    <div
      class="animation-head"
      id="animate-one"
      :class="{ 'animate-fade-in': showAnimateOne }"
    >
      <q-btn
        flat
        class="cstm-cta-two"
        style="background: white; color: #40e2e8"
        label="풀타임, 파트타임"
      />
    </div>
    <div
      class="animation-headline animated animatedFadeInUp fadeInUp"
      id="animate-two"
      :class="{ 'animate-fade-in-up': showAnimateTwo }"
    >
      <h1>
        최고의 실력을 가진<br />
        외국인 인재를 찾고 계신가요?
      </h1>
    </div>
    <div
      class="animation-subheadline animated animatedFadeInUp fadeInUp"
      id="animate-three"
      :class="{ 'animate-fade-in-up': showAnimateThree }"
    >
      <p>
        법률 및 인사관리 부담없이<br />
        1주일 이내에 원격으로 채용해보세요.
      </p>
      <p><span>개발자가 필요하신가요?</span></p>
    </div>
    <div
      class="box-features"
      id="animate-four"
      :class="{ 'animate-fade-in': showAnimateFour }"
    >
      <div class="row">
        <div class="col-md-4">
          <div class="item-features">
            <hr />
            <div class="content-features">
              <p>평균 월 120만원</p>
              <p><span>임금을 해당 국가를 기준으로 계산합니다.</span></p>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="item-features">
            <hr />
            <div class="content-features">
              <p>최대 3회 인력교체</p>
              <p><span>막상 채용해보니 맞지 않아도 걱정하지 마세요.</span></p>
            </div>
          </div>
        </div>
        <div class="col-md-4">
          <div class="item-features">
            <hr />
            <div class="content-features">
              <p>평균 3일, 최대 10일</p>
              <p>
                <span
                  >급하게 사람이 필요한 경우에도 빠른 채용이 가능합니다.</span
                >
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CstmAnimation",
  data() {
    return {
      show: true,
      showAnimateOne: false,
      showAnimateTwo: false,
      showAnimateThree: false,
      showAnimateFour: false,
    };
  },
  mounted() {
    // Trigger animations after a delay
    setTimeout(() => {
      this.showAnimateOne = true;
    }, 300);
    setTimeout(() => {
      this.showAnimateTwo = true;
    }, 0);
    setTimeout(() => {
      this.showAnimateThree = true;
    }, 0);
    setTimeout(() => {
      this.showAnimateFour = true;
    }, 500);
  },
};
</script>

<style scoped>
.animation-head,
.animation-headline,
.animation-subheadline,
.box-features {
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
}

.animate-fade-in {
  opacity: 1;
}

.animate-fade-in-up {
  opacity: 1;
  transform: translateY(0);
  transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
}
</style>
