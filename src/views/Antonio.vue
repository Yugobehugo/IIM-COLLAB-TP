<template>
  <div class="container">
    <header>
      <i class="fa fa-bars" aria-hidden="true"></i>
    </header>
    <main>
      <div class="row">
        <div class="left col-lg-4">
          <div class="photo-left">
            <img
              class="photo"
              src="https://avatars.githubusercontent.com/u/19547805"
            />
            <div class="active"></div>
          </div>
          <h4 class="name">Georges Antonio Indrianjafy</h4>
          <p class="info">FullStack dev</p>
          <p class="info">React/Node/Golang</p>

          <p class="desc">
            A random project I built:

            <a target="_blank" :href="project?.url">
              {{ project?.description }}
            </a>
          </p>

          <div>
            <button class="btn" v-on:click="getRandomProject">shuffle</button>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script>
const projects = [
  {
    url: "https://recap.antogin.dev/",
    description: "A Monthly spotify recap",
  },
  {
    url: "https://player.antogin.dev/",
    description: "Music Player",
  },
  {
    url: "https://qr.antogin.dev",
    description: "QR code reader",
  },
  {
    url: "https://pwd.antogin.dev",
    description: "Password generator",
  },
  {
    url: "https://sugar.antogin.dev/",
    description: "Diabetes / Glucodes calculator",
  },
];

export default {
  name: "Antonio",
  data() {
    return {
      project: {
        url: "https://recap.antogin.dev/",
        description: "A Monthly spotify recap",
      },
    };
  },
  methods: {
    getRandomProject() {
      console.log(this.project);
      this.project = projects.filter(
        (el) => el.description !== this.project.description
      )[Math.floor(Math.random() * (projects.length - 1 ?? 0))];
    },
  },
};
</script>

<style scoped>
.container {
  max-width: 1250px;
  margin: 30px auto 30px;
  padding: 0 !important;
  width: 90%;
  background-color: #fff;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1), 0 3px 6px rgba(0, 0, 0, 0.1);
}

header {
  background: #eee;
  background-image: url("https://images.pexels.com/photos/1731427/pexels-photo-1731427.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260");
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  height: 250px;
}

header i {
  position: relative;
  cursor: pointer;
  right: -96%;
  top: 25px;
  font-size: 18px;
  color: #fff;
}

@media (max-width: 800px) {
  header {
    height: 150px;
  }

  header i {
    right: -90%;
  }
}

main {
  padding: 20px 20px 0px 20px;
}

.left {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.photo {
  width: 200px;
  height: 200px;
  margin-top: -120px;
  border-radius: 100px;
  border: 4px solid #fff;
}

.name {
  margin-top: 20px;
  font-weight: 600;
  font-size: 18pt;
  color: #777;
}

.info {
  margin-top: -5px;
  margin-bottom: 5px;
  font-size: 11pt;
  color: #aaa;
}

.stats {
  margin-top: 25px;
  text-align: center;
  padding-bottom: 20px;
  border-bottom: 1px solid #ededed;
}

.desc {
  text-align: center;
  margin-top: 25px;
  margin: 25px 40px;
  color: #999;
  font-size: 25pt;
  padding-bottom: 25px;
  border-bottom: 1px solid #ededed;
}

.right {
  padding: 0 25px 0 25px !important;
}

.btn {
  cursor: pointer;
  padding: 0.35em 1.2em;
  border: 0.1em solid #000;
  margin: 0 0.3em 0.3em 0;
  border-radius: 0.12em;
  color: #ffffff;
  background-color: #000;
  text-align: center;
  transition: all 0.2s;
  margin-bottom: 20px;
}
.btn:hover {
  color: #000;
  background-color: #eee;
}

a:visited {
  color: #42b983;
}
</style>
