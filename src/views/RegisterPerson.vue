<!-- <template>
  <div class="backgroundTint" v-bind:class="{exited, back}" id="addPa">
    <div class="addPDialog">
      <h2>REGISTER</h2>
      <br />
      For right now just click off of this to exit. (will be fixed later)
      <form v-on:submit.prevent="addPart">
        First Name:
        <input name="firstName" type="text" v-model="firstName" />
        <br />
        Last Name:
        <input name="lastName" type="text" v-model="lastName" />
        <br />
        Number of minutes already read:
        <input name="minutes" type="number" value=0 v-model="minutes" />
        <br />
        Grade:
        <select name="grade" v-model="grade">
          <option value="1">
            1st Grade
          </option>
          <option value="1">
            2nd Grade
          </option>
          <option value="1">
            3rd Grade
          </option>
          <option value="1">
            4th Grade
          </option>
          <option value="1">
            5th Grade
          </option>
          <option value="1">
            6th Grade
          </option>
          <option value="1">
            7th Grade
          </option>
          <option value="1">
            8th Grade
          </option>
          <option value="1">
            9th Grade
          </option>
          <option value="1">
            10th Grade
          </option>
          <option value="1">
            11th Grade
          </option>
          <option value="1">
            12th Grade
          </option>
        </select>
        <br />
        Above 5 years old:
        <input type="checkbox" name="old5" v-model="greaterFive" />
        <br />
        Email (or Parents):
        <input type="email" name="participantEmail" v-model="participantEmail" />
        <br />
        Parent username (if applicable):
        <input type="username" name="parentUsername" v-model="parentUsername" />
        <br />
        Only login through parent:
        <input type="checkbox" name="parentLogin" v-model="useParent" />
        <br />
        Participant username:
        <input type="username" name="participantUsername" v-model="partUser" />
        <br />
        Participant password:
        <input type="password" name="participantPassword" v-model="partPass" />
        <br />
        <button type="submit">REGISTER</button>
      </form>
    </div>
    <div class="signinblank" id="signinblank" v-on:click="removePVue();"></div>
  </div>
</template> -->
