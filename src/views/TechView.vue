<script lang="ts">
import TabView from './TabView.vue'
import ResumeItem from '../components/ResumeItem.vue'
export default {
  components: { ResumeItem, TabView },
  data() {
    return {
      experiences: [
        {
          id: 1,
          role: 'Frontend Engineer',
          company: 'CONROO',
          location: 'Remote, EU',
          dates: '05.2023 - current',
          hightlights: [
            {
              id: 0,
              text: 'Designing and implementating Vue software components and applications for best customer experience'
            },
            {
              id: 1,
              text: 'Identifying, documenting, and communicating technical improvements to rest of team'
            },
            { id: 2, text: 'Managing environments and releases' }
          ]
        },
        {
          id: 2,
          role: 'Frontend Engineer',
          company: 'Freelance',
          location: 'Remote, USA',
          dates: '12.2022 - 04.2023',
          hightlights: []
        },
        {
          id: 3,
          role: 'Frontend Engineer',
          company: 'NextBite',
          location: 'Remote, USA',
          dates: '08.2021 - 07.2022',
          hightlights: []
        },
        {
          id: 4,
          role: 'Fullstack Engineer',
          company: 'Mount Sinai Health',
          location: 'New York, USA',
          dates: '02.2019 - 07.2021',
          hightlights: []
        },
        {
          id: 5,
          role: 'Solutions Engineer',
          company: 'Eigen Technologies',
          location: 'New York, USA',
          dates: '10.2017 - 01.2019',
          highlights: [
            {
              id: 0,
              text: 'Developed data-parsing algorithm to match incoming bank information with existing db entries (utilized in important POC).'
            },
            {
              id: 1,
              text: 'Played key role in improving document-parsing pipeline for major client, fixing bugs and adding new features in Python.'
            }
          ]
        }
      ]
    }
  }
}
</script>
<template>
  <TabView>
    <div class="resume-container">
      <h1>Summary</h1>
      <p>
        Frontend engineer with 4 years of professional experience across the stack. Alum of Bard
        College '17, hackNY '17, and StartupBus '22. NY -> Berlin.
      </p>
      <h1>Skills</h1>
      <p>
        Javascript, Typescript, HTML, CSS, React, Vue, NextJs, D3, Cypress, Storybook, CircleCI,
        PostgresQL.
      </p>
      <h1>Experience</h1>
      <ResumeItem
        v-for="exp in experiences"
        :key="exp.id"
        :role="exp.role"
        :company="exp.company"
        :location="exp.location"
        :dates="exp.dates"
        :highlights="exp.highlights"
      />

      <h2>Education</h2>
      <h2>Honors</h2>
    </div>
  </TabView>
</template>

<style>
@media (min-width: 1024px) {
  h1 {
    font-size: x-large;
  }
  h2 {
    font-size: large;
  }
  .resume-container {
    height: 100%;
    width: 90%;
  }
}
</style>
