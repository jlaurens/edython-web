<template>
  <div id="page-content">
    <b-container>
      <b-row>
        <b-col>
          <div class="container">
            <img @click="doDownload" src="../../assets/download256.png">
            <h2 @click="doDownload">Télécharger</h2>
          </div>
        </b-col>
        <b-col>
          <div class="container">
            <img src="../../assets/play256.png" @click="doPlay">
            <h2 @click="doPlay">Essayer en ligne</h2>
          </div>
        </b-col>
        <b-col>
          <div class="container">
            <img @click="doBlog" src="../../assets/blog256.png">
            <h2 @click="doBlog">Journal de bord</h2>
          </div>
        </b-col>
      </b-row>
    </b-container>
    <div id="version">
      <p>ATTENTION : application en cours de développement. La version en ligne comporte moins de fonctionnalités que la version à télécharger</p>
    </div>
    <div id="contact">
      Pour obtenir des informations complémentaires, <span class="link" @click="doContact">contacter l'équipe de développement</span>.
      <br/>
      Application sous <span class="link" @click="doLicense">licence libre EUPL 1.2</span>. Pour des corrections ou des améliorations, <span class="link" @click="doDevelopment">consulter le site de développement.</span>
    </div>
    <b-modal ref="downloadModalRef" centered title="Téléchargement" @ok="doDownloadOk">
        <div class="d-block text-center">
          <h3>Téléchargement disponible pour MacOS seulement, désolé. Les versions Windows et Linux arrivent bientôt. En attendant vous pouvez essayer la version en ligne.</h3>
        </div>
      </b-modal>
    </div>
</template>

<script>
export default {
  name: 'page-content',
  methods: {
    doContact () {
      window.open('mailto:jlaurens@edython.eu?subject=[Edython:Question]%20Mon%20sujet')
    },
    doLicense () {
      window.open('https://joinup.ec.europa.eu/collection/eupl/eupl-text-11-12')
    },
    doDevelopment () {
      window.open('https://github.com/jlaurens/edython')
    },
    doDownload () {
      this.$refs.downloadModalRef.show()
    },
    hideDownloadModal () {
      this.$refs.downloadModalRef.hide()
    },
    doDownloadOk () {
      window.open('http://download.edython.eu', '_self')
    },
    doPlay () {
      window.open('http://playground.edython.eu', '_self')
    },
    doBlog () {
      window.open('http://info.edython.eu', '_self')
    }
  }
}
</script>

<style scoped>
  #page-content {
    padding-bottom: 2rem;
  }
  h2 {
    padding-top:1rem;
    padding-bottom:0.75rem;
    font-weight: bold;
  }
  span.link {
    text-decoration: underline;
  }
  h2:hover, .container img:hover, span.link:hover {
    color: #f9951b;
    cursor: pointer;
  }
  .container {
    text-align: center;
  }
  #version {
    width: 100%;
    background-color: #98959b;
    color: white;
    font-weight: bold;
    font-size:110%;
    text-align: left;
    padding-left: 1rem;
    padding-right: 1rem;
  }
  #contact {
    font-size:110%;
    text-align: left;
    padding-left: 1rem;
    padding-right: 1rem;
  }
</style>
