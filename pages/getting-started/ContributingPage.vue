<template lang="pug">
  doc-view
    template(slot-scope="{ namespace }")
      section#reporting-issues
        section-head(:value="`${namespace}.issuesHeader`")
        div.mb-3
          ul.browser-list
            li
              markdown(:source="$t(`${namespace}.issue1`)")
            ul.browser-list
              li
                markdown(:source="$t(`${namespace}.issue2`)")
            li
              markdown(:source="$t(`${namespace}.issue3`)")
            li
              markdown(:source="$t(`${namespace}.issue4`)")
            li
              markdown(:source="$t(`${namespace}.issue5`)")
            li
              markdown(:source="$t(`${namespace}.issue6`)")
      section#pull-requests
        section-head(:value="`${namespace}.pullRequestsHeader`")
        div.mb-3
          ul.browser-list
            li(
              v-for="n in 3"
              :key="n"
            )
              markdown(:source="$t(`${namespace}.pullRequest${n}`)")
      section#local-dev
        section-head(:value="`${namespace}.localDevHeader`")
        section-text(:value="`${namespace}.localDevText1`").mb-5
        markup(lang="cli").mb-5
          | $ git clone git@github.com:vuetifyjs/vuetify
        section-text(:value="`${namespace}.localDevText2`").mb-5
        markup(lang="cli").mb-5
          | $ git checkout dev
          | $ yarn // or npm install
          | $ yarn dev // or npm run dev
        section-text(:value="`${namespace}.localDevText3`")
</template>
