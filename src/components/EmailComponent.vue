<template>
  <q-item>
    <q-item-section>
      <q-card id="card" class="bg-secondary rounded shadow-2">
        <q-card-section>
          <div class="row text-body1 flex align">
            <span id="sender" class="">{{ sender }}</span>
            <span id="-" class="flex justify-center q-px-md">-</span>
            <span id="subject" class="">{{ subject }}: </span>
            <span
              id="description"
              class="col text-body2 q-pl-sm text-grey-6 overflow"
            >
              {{ description }}
            </span>
          </div>
        </q-card-section>
      </q-card>
    </q-item-section>
  </q-item>
</template>

<script setup>
defineProps(['sender', 'subject', 'description']);
</script>

<style lang="scss" scoped>
#card {
  width: 100%;
}
.overflow {
  text-overflow: ellipsis;
  white-space: nowrap;
  overflow: hidden;
}
.align {
  align-items: first baseline;
}

.rounded {
  border-radius: 1.5em;
}
</style>
