<template>
<div>
  <div v-if="user" class="header">
    <div>
      <h2>{{user.firstName}} {{user.lastName}}</h2>
    </div>
    <div class="button">
      <p><button @click=" logout" class="pure-button pure-button-primary">Logout</button></p>
    </div>

    <div class="containerDash">
      <div class="topDash">
        <div class="totalP">
          Total Number of Participants: {{participants.length}}
        </div>
        <router-link to="/register" class="addP" id="addParticipant">
          <svg class="addSVG">
            <circle class="circleClass"></circle>
            <line x1="2.5vh" y1="1vh" x2="2.5vh" y2="4vh" class="lineClass"></line>
            <line x1="1vh" y1="2.5vh" x2="4vh" y2="2.5vh" class="lineClass"></line>
          </svg>
          <div class="addPInside">
            ADD PARTICIPANT
          </div>
        </router-link>
      </div>
      <div class="namesP names">
        List Of Participants:
        <div class="searchP">
          Search
        </div>
        <div class="listNames">
          <div class="fdivider">
            <div class="contain">
              <br />
              Name:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.firstName}} {{participant.lastName}}
              </div>
            </div>
          </div>
          <div class="gDivider">
            <div class="contain">
              <br />
              Grade:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.grade}}
              </div>
            </div>
          </div>
          <div class="gDivider">
            <div class="contain">
              Minutes Read:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.minutesRead}}
              </div>
            </div>
          </div>
          <div class="divider">
            <div class="contain">
              <br />
              Username:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.username}}
              </div>
            </div>
          </div>
        </div>
        <div class="bottomButton1">
          <div class="emailP">
            EMAIL
          </div>
          <div class="textP">
            TEXT
          </div>
        </div>
      </div>
      <div class="signedP names">
        List Of Participants (signed on in the past week):
        <div class="searchP">
          Search
        </div>
        <div class="listNames">
          <div class="fdivider">
            <div class="contain">
              <br />
              Name:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.firstName}} {{participant.lastName}}
              </div>
            </div>
          </div>
          <div class="gDivider">
            <div class="contain">
              <br />
              Grade:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.grade}}
              </div>
            </div>
          </div>
          <div class="gDivider">
            <div class="contain">
              Minutes Read:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.minutesRead}}
              </div>
            </div>
          </div>
          <div class="divider">
            <div class="contain">
              <br />
              Username:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.username}}
              </div>
            </div>
          </div>
        </div>
        <div class="bottomButton2">
          <div class="emailP">
            EMAIL
          </div>
          <div class="textP">
            TEXT
          </div>
        </div>
      </div>
      <div class="haventSignedP names">
        List Of Participants (not signed on in the past week):
        <div class="searchP">
          Search
        </div>
        <div class="listNames">
          <div class="fdivider">
            <div class="contain">
              <br />
              Name:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.firstName}} {{participant.lastName}}
              </div>
            </div>
          </div>
          <div class="divider">
            <div class="contain">
              <br />
              Grade:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.grade}}
              </div>
            </div>
          </div>
          <div class="divider">
            <div class="contain">
              Minutes Read:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.minutesRead}}
              </div>
            </div>
          </div>
          <div class="divider">
            <div class="contain">
              <br />
              Username:
            </div>
            <div class="borderContain">
              <div class="contain" v-for="(participant) in participants">
                {{participant.username}}
              </div>
            </div>
          </div>
        </div>
        <div class="bottomButton3">
          <div class="emailP">
            EMAIL
          </div>
          <div class="textP">
            TEXT
          </div>
        </div>
      </div>
    </div>
  </div>
  <div v-else>
    <p>If you would like to upload photos, please register for an account or login.</p>
    <router-link to="/register" class="pure-button">Register</router-link> or
    <router-link to="/login" class="pure-button">Login</router-link>
  </div>
</div>
</template>

<script>
export default {
  name: 'mypage',
  computed: {
    user() {
      return this.$store.state.user;
    },
    participants() {
      return this.$store.state.participants;
    }
  },
  created() {
    this.$store.dispatch("getUser");
    this.$store.dispatch("getParticipants");
  },
  methods: {
    async logout() {
      try {
        this.error = await this.$store.dispatch("logout");
      } catch (error) {
        console.log(error);
      }
    },
  }
}
</script>

<style>
.containerDash{
  width: 90vw;
  left: 5vw;
  position: relative;
}
.names{
  display: inline-block;
  height: 80vh;
  width: 29vw;
  border-radius: 10px;
  position: absolute;
  font-size: 1.15vw;
}
.totalP{
  width: 27.5vw;
  margin-right: .5vw;
  margin-top: 2vh;
  margin-bottom: 2vh;
  border-radius: 5px;
  padding: .25vh;
  padding-top:.75vh;
  padding-bottom: 1vh;
  display: inline-block;
  vertical-align: top;
  border-color: #47cdc6;
  border-width: .5vw;
  border-radius: 10px;
  border-style: solid;
  color: rgba(240,240,240,1);
  font-family: sans-serif;
  font-size: 2vw;
}
.addP{
  position: relative;
  display: inline-block;
  width:27.7vw;
  margin: .5vw;
  margin-top: 2vh;
  margin-bottom: 2vh;
  padding: .25vh;
  border-color: #47cdc6;
  border-width: .5vw;
  border-radius: 10px;
  border-style: solid;
  vertical-align: top;
}
.addPInside{
  display: inline-block;
  padding: 1.25vh;
  padding-top: .75vh;
  padding-bottom: .5vh;
  vertical-align: top;
  color: rgba(240,240,240,1);
  font-family: sans-serif;
  font-size: 2vw;
}
.addSVG{
  width: 5vh;
  height: 5vh;
}
.circleClass{
  cx:2.5vh;
  cy:2.5vh;
  r: 2.25vh;
  stroke-width: .25vh;
  stroke: #47cdc6;
  fill: #47cdc6;
}
.lineClass{
  stroke: white;
  stroke-width: 10px;
  stroke-linecap: round;
}
.namesP{
  background-color: #47cdc6;
  left:0vw;
  border-style: solid;
  border-color: rgba(240,240,240,1);
  border-width: 6px;
  padding: 4px;
  font-family: sans-serif;
}
.signedP{
  background-color: #c7f65a;
  left: 30vw;
  border-style: solid;
  border-color: rgba(240,240,240,1);
  border-width: 6px;
  padding: 4px;
  font-family: sans-serif;
}
.haventSignedP{
  background-color: #c64d56;
  left: 60vw;
  border-style: solid;
  border-color: rgba(240,240,240,1);
  border-width: 6px;
  padding: 4px;
  font-family: sans-serif;
}
.emailP{
  position: relative;
  width: 5vw;
  border-style: solid;
  border-radius: 1vw;
  border-width: 4px;
  display: inline-block;
  margin: 0px;
  text-align: center;
  left: 5vw;
  background-color: rgba(51,51,51,1);
  padding: .5vw;
  color: rgba(240,240,240,1);
  top: 0vh;
}
.textP{
  position: relative;
  width: 5vw;
  border-style: solid;
  border-radius: 1vw;
  border-width: 4px;
  display: inline-block;
  margin: 0px;
  text-align: center;
  left: 10vw;
  background-color: rgba(51,51,51,1);
  padding: .5vw;
  color: rgba(240,240,240,1);
  top: 0vh;
}
.bottomButton1{
  position: absolute;
  bottom: 5vh;
}
.bottomButton2{
  position: absolute;
  bottom: 5vh;
}
.bottomButton3{
  position: absolute;
  bottom: 5vh;
}
.addPDialog{
  width: 50vw;
  position: fixed;
  height: 45vh;
  background-color: rgba(210,240,260,1);
  z-index: 5;
  left: 25vw;
  top: 20vh;
  text-align: center;
  padding-top: 10vw;
}
/* .addPDialog form{
  text-align: left;
  position: relative;
  top: 12.5vh;
  left: 10vw;
  width: 90%;
} */

.fdivider{
  display:inline-block;
  width: 8vw;
  vertical-align: top;
  overflow: hidden;
}
.divider{
  display:inline-block;
  width: 4vw;
  vertical-align: top;
  overflow:hidden;
}
.gDivider{
  display:inline-block;
  width: 3.5vw;
  vertical-align: top;
  overflow:hidden;
}

.edit{
  display:inline-block;
  width: 2.5vw;
  vertical-align: top;
}
.delete{
  display:inline-block;
  width: 2.5vw;
  vertical-align: top;
}
.borderContain{
  height: 55vh;
  border-style: dotted;
  border-color: rgba(51,51,51,1);
}
.contain {
  height: 60px;
  overflow: hidden;
}
</style>
