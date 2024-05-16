<template>
  <div class="cstm-container">
    <q-header elevated class="cstm-header">
      <q-toolbar class="toolbar-cstm">
        <!-- Left column for logo -->
        <div class="col-4">
            <img :src="logoSrc" alt="Logo" title="Logo" style="height: 21px; width: 114px">
        </div>

        <!-- Center column for dropdown -->
        <div class="col-4 text-center">
          <div class="q-pa-md main-menu">
            <q-btn-dropdown flat color="primary" label="채용">
              <q-list>
                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>채용</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>해외 개발자 원격 채용</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>외국인 원격 채용 (비개발 직군)</q-item-label>
                  </q-item-section>
                </q-item>

                <q-item clickable v-close-popup @click="onItemClick">
                  <q-item-section>
                    <q-item-label>한국어 가능 외국인 채용</q-item-label>
                  </q-item-section>
                </q-item>
              </q-list>
            </q-btn-dropdown>
            <q-btn flat style="background: none; color: white" label="해외 개발자 활용 서비스" />
          </div>
        </div>

        <!-- Right column for q-btn -->
        <div class="col-4 text-right">
          <div class="q-pa-md q-gutter-sm">
            <q-btn class="cstm-cta" style="background: white; color: #4A77FF" label="문의하기" />
          </div>
        </div>
      </q-toolbar>
    </q-header>
  </div>
</template>

<script>
// Import the logo image
import logoSrc from 'assets/images/logo.svg';

export default {
  name: 'CstmHeader',
  setup () {
    // Return the logoSrc to be used in the template
    return {
      logoSrc: logoSrc
    }
  }
}
</script>
