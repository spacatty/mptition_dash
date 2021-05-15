<template>
  <q-page class="q-pa-md relative">
    <div class="q-pa-md flex column items-center justify-between">
      <q-virtual-scroll :items="heavyList" class="virtualScroll">
        <template v-slot="{ item, index }">
          <q-item v-ripple="{ color: 'black' }" :key="index">
            <q-item-section>
              <q-item-label> #{{ index }} - {{ item.label }} </q-item-label>
            </q-item-section>
            <q-item-section avatar>
              <q-fab
                color="primary"
                icon="keyboard_arrow_left"
                direction="left"
                flat
              >
                <q-fab-action color="negative" icon="delete_outline" flat />
                <q-fab-action color="primary" icon="mode_edit_outline" flat />
              </q-fab>
            </q-item-section>
          </q-item>
        </template>
      </q-virtual-scroll>
    </div>
  </q-page>
</template>

<script>
const maxSize = 100;
const heavyList = [];

for (let i = 0; i < maxSize; i++) {
  heavyList.push({
    label:
      "Lorem ipsum dolor, sit amet consectetur adipisicing elit " + (i + 1),
  });
}

Object.freeze(heavyList);

export default {
  name: "manageUsersComponent",
  data() {
    return {
      heavyList,
    };
  },
  methods: {},
  created() {
    console.log("i am created");
  },
};
</script>

<style scoped>
.virtualScroll {
  max-height: 80vh;
  min-width: 50vw;
}
.buttonContainer {
  width: 100%;
}
</style>