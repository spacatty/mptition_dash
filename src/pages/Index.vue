<template>
  <q-layout view="hHh lpR fFf">
    <q-header elevated flat class="q-pa-md bg-dark text-white flex flex-center">
      <q-tabs
        v-model="tab"
        narrow-indicator
        dense
        align="center"
        class="text-whie"
      >
        <q-tab
          :ripple="{ color: 'white' }"
          name="manageNews"
          icon="unsubscribe"
          label="Новости"
        />
        <q-tab
          :ripple="{ color: 'white' }"
          name="manageCompetitions"
          icon="emoji_events"
          label="Соревнования"
        />
        <q-tab
          :ripple="{ color: 'white' }"
          name="manageUsers"
          icon="person"
          label="Пользователи"
        />
      </q-tabs>
    </q-header>
    <q-page-container class="pContainer">
      <q-tab-panels
        v-model="tab"
        animated
        swipeable
        transition-prev="fade"
        transition-next="fade"
        class="flex flex-center"
      >
        <q-tab-panel class="q-pa-none bg-grey-1 h-full" name="manageNews">
          <manageNewsComponent />
        </q-tab-panel>
        <q-tab-panel class="q-pa-none bg-grey-1" name="manageCompetitions">
          <mangeCompetitionsComponent />
        </q-tab-panel>
        <q-tab-panel class="q-pa-none bg-grey-1" name="manageUsers">
          <manageUsersComponent />
        </q-tab-panel>
      </q-tab-panels>
    </q-page-container>
  </q-layout>
</template>

<script>
import manageNewsComponent from "../components/manageNewsComponent";
import mangeCompetitionsComponent from "../components/mangeCompetitionsComponent";
import manageUsersComponent from "../components/manageUsersComponent";

export default {
  name: "PageIndex",
  components: { manageNewsComponent, mangeCompetitionsComponent, manageUsersComponent },
  data() {
    return {
      tab: "manageNews",
    };
  },
};
</script>
