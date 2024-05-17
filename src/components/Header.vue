<template>
  <div class="cstm-container">
    <q-header elevated class="cstm-header">
      <q-toolbar class="toolbar-cstm">
        <!-- Left column for logo -->
        <div class="col-4">
          <img
            :src="logoSrc"
            alt="Logo"
            title="Logo"
            style="height: 21px; width: 114px"
          />
        </div>

        <!-- Center column for dropdown -->
        <div class="col-4 text-center outer-main-menu desktop-only">
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
            <q-btn
              flat
              style="background: none; color: white"
              label="해외 개발자 활용 서비스"
            />
          </div>
        </div>

        <!-- Right column for q-btn -->
        <div class="col-4 text-right outer-cta-btn desktop-only">
          <div class="q-pa-md q-gutter-sm">
            <q-btn
              class="cstm-cta"
              style="background: white; color: #4a77ff"
              label="문의하기"
            />
          </div>
        </div>

        <!-- Hamburger Menu Button (Mobile Only) -->
        <div class="col-8 text-right mobile-only cstm-btn-mobile">
          <q-btn flat round icon="menu" @click="toggleDrawer" />
        </div>
      </q-toolbar>
    </q-header>
    <!-- Drawer for Mobile Menu -->
    <q-drawer v-model="drawer" side="right" overlay>
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

        <q-item clickable v-close-popup @click="onItemClick">
          <q-item-section>
            <q-item-label>해외 개발자 활용 서비스</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-drawer>
  </div>
</template>

<script>
import { ref } from "vue"; // Import ref from Vue
// Import the logo image
import logoSrc from "assets/images/logo.svg";

export default {
  name: "CstmHeader",
  setup() {
    const drawer = ref(false);

    const toggleDrawer = () => {
      drawer.value = !drawer.value;
    };

    return {
      logoSrc,
      drawer,
      toggleDrawer,
    };
  },
};
</script>
