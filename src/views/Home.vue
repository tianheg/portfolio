<template>
  <div class="container">
    <div id="name-container">
      <img id="avatar" src="./../assets/images/av.png" alt="avatar" />
      <h1>tianheg</h1>
    </div>
    <div class="title-desc-container">
      <a id="github" href="https://github.com/tianheg" target="_blank" rel="noopener noreferrer"
        ><img class="title-font" src="./../assets/images/github.svg" />Develop</a
      >
      <span>/</span>
      <a id="blog" href="https://blog.yidajiabei.xyz" target="_blank" rel="noopener noreferrer"
        ><img class="title-font" src="./../assets/images/zeit.svg" />Blog</a
      >
    </div>
    <div class="article">
      <h2>WHO AM I</h2>
      <p>
        I'm <i>tianheg</i>. You may know me from GitHub or other places.
      </p>

      <h2>Academics</h2>
      <ul>
        <li>
          🙇 Not graduate at 🇨🇳
          <a href="http://www.lnpu.edu.cn/" target="_blank" rel="noopener noreferrer">Liaoning University of Petroleum and Chemical Technology</a
          >, <i>BE in Electronic and Information Engineering</i>.
        </li>
        <li>🔭 <b>Fields of interest:</b> CyberSecurity / Web Application.</li>
      </ul>

      <h2>Devices</h2>
      <ul>
        <li>HP Notebook - 14s-cr0006tx / document: <a href="https://support.hp.com/us-en/document/c06002209">en</a> &bull; <a href="https://support.hp.com/cn-zh/document/c06002212">cn</a></li> 
        <li>vivo y85</li>
      </ul>

      <h2>How can we trust you!</h2>
      <p>
        I have verified my identity with a GPG signature which proves my ownership of this domain. (See the cryptography
        proof here:
        <a href="https://keybase.io/yidajiabei/sigchain#d779cd2e9218b1a81f56f15007196fa0484e70d7145b390dadd62038e44f58500f"
          target="_blank"
          rel="noopener noreferrer"
          >Keybase - claimed ownership of <b>yidajiabei.xyz</b> via dns</a
        >.) In other words, <i>I AM LEGIT HERE.</i>
      </p>
      <p>
        I have my GPG public key hosted on
        <a href="http://keybase.io/yidajiabei" target="_blank" rel="noopener noreferrer">Keybase - tianheg</a>. You
        can pull and import my GPG public key with:
      </p>
      <pre>curl https://keybase.io/yidajiabei/pgp_keys.asc | gpg --import</pre>
      <p>
        If you see a commit on GitHub which is linked to my username / account / email,
        <b>please keep in mind that it may not actually be me!</b> (Unless it shows a green <code>verified</code> badge,
        which means that I have signed the commit with my GPG private key, claiming the authorship of the commit.)
      </p>

      <h2>Contacts</h2>
      <ul>
        <li>
          <b>Email：</b>
          <a href="mailto:yidajiabei@gmail.com">yidajiabei#gmail.com</a><i> (Preferred)</i>
        </li>
      </ul>
    </div>
  </div>
</template>

<style lang="css" scoped>
#name-container {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
}

#avatar {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  margin-right: 12px;
}

#copyright:hover {
  border: none;
}

.title-font {
  width: 16px;
  height: 16px;
  margin-right: 4px;
}

.title-desc-container {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin: 8px 0;
}

.title-desc-container a {
  display: flex;
  align-items: center;
}

.title-desc-container span {
  margin: 0px 4px;
}

.title-desc-container #github {
  color: #24292e;
}

.title-desc-container #blog {
  color: #0070f3;
}
</style>
