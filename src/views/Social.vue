<template>
  <div class="container">
    <h1>Social</h1>
    <p>Some of my followers.</p>

    <div class="col-container">
      <div class="row-container">
        <statCard
          statTitle="RSS"
          :followers="rss.data"
          suffix="subscribers"
          icon="rss.png"
          :loading="rss.loading"
          link="https://blog.yidajiabei.xyz/index.xml"
        />
      </div>
      <div class="row-container">
        <statCard
          statTitle="Twitter"
          :followers="twitter.data"
          suffix="followers"
          icon="twitter.png"
          :loading="twitter.loading"
          link="https://twitter.com/yidajiabei"
        />
        <statCard
          statTitle="GitHub"
          :followers="github.data"
          suffix="followers"
          icon="github.png"
          :loading="github.loading"
          link="https://github.com/tianheg"
        />
      </div>
    </div>
  </div>
</template>

<script>
import statCard from '@/components/StatCard.vue'

export default {
  components: {
    statCard,
  },
  data() {
    return {
      rss: { data: 0, loading: true },
      twitter: { data: 0, loading: true },
      github: { data: 0, loading: true },
    }
  },
  mounted() {
    const apiUrl = 'https://api.spencerwoo.com/substats'
    const rssUrl = 'https://blog.yidajiabei.xyz/index.xml'

    const rssAxios = this.axios.get(`${apiUrl}/?source=feedly|inoreader|feedsPub&queryKey=${rssUrl}`)
    const twitterAxios = this.axios.get(`${apiUrl}/?source=twitter&queryKey=yidajiabei`)
    const githubAxios = this.axios.get(`${apiUrl}/?source=github&queryKey=yidajiabei`)
    const telegramAxios = this.axios.get(`${apiUrl}/?source=telegram&queryKey=yidajiabei`)

    rssAxios.then(r => {
      this.rss = { data: r.data.data.totalSubs, loading: false }
    })
    twitterAxios.then(r => {
      this.twitter = { data: r.data.data.totalSubs, loading: false }
    })
    githubAxios.then(r => {
      this.github = { data: r.data.data.totalSubs, loading: false }
    })
    telegramAxios.then(r => {
      this.telegram = { data: r.data.data.totalSubs, loading: false }
    })
  },
}
</script>

<style lang="css" scoped>
.col-container {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: flex-start;
  align-items: stretch;
  align-content: center;
}

.row-container {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: center;
  align-items: stretch;
  align-content: stretch;
  margin: 15px 0px;
}

.row-container .statCard:last-child {
  margin-left: 30px;
}

.row-container .statCard {
  flex: 1;
}

@media screen and (max-width: 760px) {
  .row-container {
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    justify-content: flex-start;
    align-items: stretch;
    align-content: center;
  }

  .row-container .statCard:last-child {
    margin-left: 0px;
    margin-top: 30px;
  }
}

#substats-footer {
  color: #666666;
  text-align: left;
}
</style>
