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
          highlights: [
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
          highlights: [
            {
              id: 0,
              text: "Revitalized a professional musician's website, seamlessly blending client needs and current design trends using React, TailwindCSS, and npm packages for image carousel and smooth scrolling."
            },
            {
              id: 1,
              text: 'Significantly expanded the reach of the site by making it mobile-friendly.'
            },
            {
              id: 2,
              text: 'Streamlined user experience to reinforce site branding and messaging; limited destinations to only a few key pages and displayed those pages as one continuous scroll.'
            },
            {
              id: 3,
              text: 'Consistently updated the website and provided valuable feedback based on evolving design trends and privacy considerations.'
            }
          ]
        },
        {
          id: 3,
          role: 'Frontend Engineer',
          company: 'NextBite',
          location: 'Remote, USA',
          dates: '08.2021 - 07.2022',
          highlights: [
            {
              id: 0,
              text: 'Built and maintained React components to address usability or business needs of client base of 300+ restaurants (e.g. implemented attention-grabbing banner and full-screen notifications for incoming orders page as well as a settings modal to choose preferred style).'
            },
            {
              id: 1,
              text: 'Promoted best practices in standards of code by proactively contributing to documentation, updating Cypress and Jest tests, pair-programming, and reviewing teammate PRs as a code owner of upcoming feature repo.'
            },
            {
              id: 2,
              text: 'Triaged client bug reports or confusing user experiences and implemented minimally invasive fixes.'
            }
          ]
        },
        {
          id: 4,
          role: 'Fullstack Engineer',
          company: 'Mount Sinai Health',
          location: 'New York, USA',
          dates: '02.2019 - 07.2021',
          highlights: [
            {
              id: 0,
              text: 'Created, communicated, and upheld development process across team to improve testability for medical messaging app used by thousands of customers daily.'
            },
            {
              id: 1,
              text: 'Added end-to-end Puppeteer JS frontend tests of happy-path and edge-case scenario flows.'
            },
            {
              id: 2,
              text: 'Collaborated with product leads to define acceptance criteria and increase coverage of edge-cases.'
            }
          ]
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
      <p>
        Bachelors in Mathematics and Computer Science | Bard College, Annandale-on-Hudson, NY USA |
        GPA 3.7
      </p>
      <h2>Honors</h2>
      <p>
        Distinguished Scientist Scholar (2013-2017), HackNY Fellow (2017), StartupBus Finalist
        (2022)
      </p>
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
