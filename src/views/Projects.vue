<template>
  <div class="container">
    <h1>Projects</h1>
    <p>Projects I participated in and/or developed.</p>

    <GitHubCard
      title="Wiki"
      link="https://github.com/tianheg/wiki"
      :info="wikiInfo"
      :loading="loading"
    >
      <p>I freaking can't believe it that this is my most starred project...</p>
    </GitHubCard>

    <GitHubCard
      title="Note"
      link="https://github.com/tianheg/wiki"
      :info="noteInfo"
      :loading="loading"
    >
      <p>What I think, read, watch, listen</p>
    </GitHubCard>

    <GitHubCard
      title="💻 My dotfiles"
      link="https://github.com/tianheg/dotfiles"
      :info="dotfilesInfo"
      :loading="loading"
    >
      <p>Store my configuration about bash, zsh, vscode, and so on</p>
    </GitHubCard>
  </div>
</template>

<script>
import GitHubCard from '@/components/GitHubCard.vue'

export default {
  components: {
    GitHubCard,
  },
  data() {
    return {
      loading: true,
      wikiInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      noteInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
      dotfilesInfo: {
        stargazers_count: 0,
        forks_count: 0,
      },
    }
  },
  mounted() {
    const githubApiUrl = 'https://api.github.com/repos'

    const wikiAxios = this.axios.get(`${githubApiUrl}/tianheg/wiki`)
    const noteAxios = this.axios.get(`${githubApiUrl}/tianheg/note`)
    const dotfilesAxios = this.axios.get(`${githubApiUrl}/tianheg/dotfiles`)

    this.axios
      .all([wikiAxios, noteAxios, dotfilesAxios])
      .then(
        this.axios.spread((...resp) => {
          this.loading = false
          this.wikiInfo = resp[0].data
          this.noteInfo = resp[1].data
          this.dotfilesInfo = resp[2].data
        }),
      )
      .catch(err => {
        this.loading = false
        // eslint-disable-next-line no-console
        console.error(err)
      })
  },
}
</script>

<style scoped>
.container .github-project-card:not(:last-child) {
  margin-bottom: 40px;
}

</style>
