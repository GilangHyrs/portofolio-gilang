<script setup>
import { defineComponent, reactive } from 'vue';

defineComponent({
    name: 'Timelines',
});

const timelines = reactive([
    {
        id: 0,
        icon: 'mdi-book-education',
        color: 'cyan lighten-1',
        title: 'University Islam Riau',
        position: 'Teknik Informatika S1',
        period: '2022',
        description: '',
    },
    {
        id: 1,
        icon: 'mdi-book-education',
        color: 'amber darken-1',
        title: 'SMAN 1 UKUI ',
        position: 'SISWA',
        period: '2019-2022',
        description: '',
    },
    {
        id: 2,
        icon: 'mdi-book-education',
        color: 'blue-darken-3',
        title: 'SMPN 1 UKUI ',
        position: 'SISWA',
        period: '2016-2019',
        description: '',
    },
    {
        id: 3,
        icon: 'mdi-book-education',
        color: 'blue-grey',
        title: 'SDN 001 UKUI',
        position: 'SISWA',
        period: '2010 — 2016',
        description: '',
    },
    {
        id: 4,
        icon: 'mdi-briefcase-variant',
        color: 'deep-orange-lighten-1',
        title: 'Anggota Osis SMAN 1 UKUI',
        position: 'Seksi bidang prestasi akademik, seni, dan/atau olahraga sesuai bakat dan minat',
        period: '2020 - 2022',
        description: 'olahraga (Bola kaki,Bola Volly)',
    },
]);
</script>

<template>
    <div class="timeline mt-5">
        <h5 class="text-h5 text-uppercase text-center text-deep-purple-accent-1">Education & work</h5>
        <v-timeline class="mt-5">
            <v-timeline-item
                v-for="timeline in timelines"
                :key="timeline.id"
                :dot-color="timeline.color"
                :icon="timeline.icon"
                size="large"
            >
                <template v-slot:opposite>
                    <div
                        :class="`pt-1 headline font-weight-bold text-button text-${timeline.color}`"
                        v-text="timeline.period"
                    ></div>
                </template>
                <div>
                    <h2 :class="`mt-n1 headline font-weight-light mb-4 text-${timeline.color}`">
                        {{ timeline.title }}
                    </h2>
                    <h5 :class="`text-button text-${timeline.color}`">{{ timeline.position }}</h5>
                    <span class="text-subtitle-2">{{ timeline.description }}</span>
                </div>
            </v-timeline-item>
        </v-timeline>
    </div>
</template>
