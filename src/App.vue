<script setup>
import parliamentChart from './components/charts/parliamentChart.vue';
import pieChart from './components/charts/pieChart.vue';
import senatePage from './components/senatePage.vue';
import partiesPage from './components/partiesPage.vue';
import lawsPage from './components/lawsPage.vue';
</script>

<script>
export default {
  props: {

  },
  data() {
    return {
      loading: false,
      page: 'home',
      player: { id: "steam:21382918", first_name: "John", last_name: "Doe", isSenator: true, party: "KNL" },
      parties: [
        { name: "Kiwa National League", label: "KNL", color: "#822831", ideology: "Center", members: [
          { id: "steam:21382418", name: "Leonard Jul", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Caucus"},
          { id: "steam:21382918", name: "Roger Walters", role: "Leader"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
        ]},
        { name: "Gran National League", label: "GNL", color: "#789FC1", ideology: "Center", members: [
          { id: "steam:21382418", name: "Jorje el Trabieso", role: "Whip"},
          { id: "steam:213632918", name: "Pablo Lopez", role: "Caucus"},
          { id: "steam:21743918", name: "Roberto Lopez", role: "WhipA"},
          { id: "steam:21382418", name: "Roger Walters", role: "Leader"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
        ]},
        { name: "The Black Hand party", label: "BH", color: "#2832E0", ideology: "Center", members: [
          { id: "steam:21382918", name: "Omar Montes", role: "Leader"},
          { id: "steam:21382418", name: "Don Omar", role: "Whip"},
          { id: "steam:213632918", name: "Felix Carrion", role: "Caucus"},
          { id: "steam:21743918", name: "Daddy Jankee", role: "WhipA"},
        ]},
        { name: "Los Santos Republican League", label: "LSRL", color: "#F85552", ideology: "Center", members: [
          { id: "steam:21382918", name: "Omar Montes", role: "Leader"},
          { id: "steam:21382418", name: "Don Omar", role: "Whip"},
          { id: "steam:213632918", name: "Felix Carrion", role: "Caucus"},
          { id: "steam:21743918", name: "Daddy Jankee", role: "WhipA"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
          { id: "steam:213632918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21743918", name: "Roger Walters", role: "Senator"},
          { id: "steam:21382418", name: "Roger Walters", role: "Senator"},
        ]},
      ],

      laws: [
        { title: "Los Santos Constitution", type: "Constitution", time: 1081442485000, jurisdiction: "Los Santos", ideology: "Center", body: "<p>Law text</p>"},
        { title: "First Amendment", type: "Amendment", time: 1681442485000, jurisdiction: "Los Santos", ideology: "Center", body: "<p>Law text</p>"},
        { title: "Weapons Bill", type: "Bill", time: -1681442485000, jurisdiction: "Los Santos", ideology: "Center", body: "<p>Law text</p>"},
        { title: "Traffic Bill", type: "Bill", time: -62111442485000, jurisdiction: "Los Santos", ideology: "Right", body: "<p>Law text</p>"},
        { title: "Logic Bill", type: "Bill", time: 1681442485000, jurisdiction: "Los Santos", ideology: "Far Right", body: "<p>Law text</p>"},
        { title: "No-Hunt Decree", type: "Regional Law", time: 1681442485000, jurisdiction: "Los Santos", ideology: "Far Right", body: "<p>Law text</p>"},
      ],
    };
  },
  methods: {
    createParty(party) {
      this.parties[this.parties.length] = party;
    },
    joinParty(party_label) {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == party_label) {
          this.player.party = party_label;
          if(this.parties[index].members.length < 1) {
            this.parties[index].members[this.parties[index].members.length] = {id: this.player.id, name: this.player.first_name + " " + this.player.last_name, role: "Leader"};
          }else {
            this.parties[index].members[this.parties[index].members.length] = {id: this.player.id, name: this.player.first_name + " " + this.player.last_name, role: "Senator"};
          }
        }
      }
    },
    leaveParty() {
      //fetch leave party
      this.removePlayerFromParty(this.player);
      this.player.party = null;
    },
    removePlayerFromParty(player) {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == player.party) {
          for (let index2 = 0; index2 < this.parties[index].members.length; index2++) {
            if(this.parties[index].members[index2].id == player.id) {
              this.parties[index].members.splice(index2, 1);
            }
          }
          if(this.parties[index].members.length < 1) {
            this.parties.splice(index, 1); //remove party
          }else {
            this.checkPartyLeadership(this.parties[index].label);
          }
        }
      }
    },
    checkPartyLeadership(label) {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == label && !this.hasLeader(this.parties[index].members)) {
          for (let i = 0; i < this.parties[index].members.length; i++) {
            if(this.parties[index].members[i].role == "Whip") {
              this.parties[index].members[i].role = "Leader";
              //ADD Control variable to randomice the leader asign in case of a non existent whip
            }
          }
        }
      }
    },
    hasLeader(members) {
      for (let index = 0; index < members.length; index++) {
        if(members[index].role == "Leader") {
          return true;
        }
      }
      return false;
    },
    calculatePie() {
      let pieList = [{name: 'Constitution',y: 0,}, {name: 'Anmenments',y: 0}, {name: 'Bills',y: 0}, {name: 'Regional Decrees',y: 0}];
      for (let index = 0; index < this.laws.length; index++) {
        switch (this.laws[index].type) {
          case "Constitution":
            pieList[0].y = pieList[0].y + 1
            break;
          case "Amendment":
            pieList[1].y = pieList[1].y + 1
            break;
          case "Bill":
            pieList[2].y = pieList[2].y + 1
            break;
          case "Regional Law":
            pieList[3].y = pieList[3].y + 1
            break;
          default:
            break;
        }
        
      }
      return pieList;
    },
    toPartyChartData() {
      let imported_data = [];
      for (let index = 0; index < this.parties.length; index++) {
        imported_data[imported_data.length] = [this.parties[index].name, Number(this.parties[index].members.length), this.parties[index].color, this.parties[index].label];
      }
      return imported_data;
    },
    getPlayerParty() {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == this.player.party) {
          return this.parties[index];
        }
      }
      return null;
    },
    getLeaders(party) {
      let leadership = { leader: null, whip: null, caucus: null, whipa: null }
      for (let index = 0; index < party.members.length; index++) {
        if(party.members[index].role == 'Leader') {
          leadership.leader = party.members[index];
        }else if(party.members[index].role == 'Whip') {
          leadership.whip = party.members[index];
        }else if(party.members[index].role == 'Caucus') {
          leadership.caucus = party.members[index];
        }else if(party.members[index].role == 'WhipA') {
          leadership.whipa = party.members[index];
        }
      }
      return leadership;
    },
    getMayorityParty(parties) {
      if(parties == null) {
        return null;
      }
      let mayority_index = 0;
      let mayority_party = { label: null, members: 0 }
      for (let index = 0; index < parties.length; index++) {
        if(parties[index].members.length > mayority_party.members) {
          mayority_party.members = parties[index].members.length;
          mayority_party.label = parties[index].label;
          mayority_index = index;
        }
      }
      mayority_party.leadership = this.getLeaders(parties[mayority_index]);
      return mayority_party
    },
    getPartyByLabel(label) {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == label) {
          return this.parties[index];
        }
      }
      return null;
    },
    getPartyIndexByLabel(label) {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == label) {
          return index;
        }
      }
      return null;
    },
    changeRoles(members, party_label) {
      for (let index = 0; index < this.parties.length; index++) {
        if(this.parties[index].label == party_label) {
          this.parties[index].members = members;
        }
      }
    },
    generateLeadership() {
      let parties_copy = JSON.parse(JSON.stringify(this.parties));
      let mayority_party = this.getMayorityParty(parties_copy);
      
      let indexMayority = this.getPartyIndexByLabel(mayority_party.label);
      parties_copy.splice(indexMayority, 1);

      let minority_party = this.getMayorityParty(parties_copy);
      return { mayority: mayority_party, minority: minority_party }
    },
    createParty(form) {
      this.parties[this.parties.length] = { name: form.name, label: form.label, color: form.color, ideology: form.ideology, members: [{ id: this.player.id, name: this.player.first_name + " " + this.player.last_name, role: "Leader"},]};
      this.player.party = form.label;
    }
  },
};
</script>

<template>
  <main>
    <div v-if="loading"></div>
    <div class="main" v-else>
      <div class="main_menu">
        <ul class="menu_list" v-if="player.isSenator">
          <li class="menu_list_item menu_list_item_active" v-if="page == 'home'"><font-awesome-icon :icon="['fas', 'house']"/></li>
          <li class="menu_list_item" v-else @click="page = 'home'"><font-awesome-icon :icon="['fas', 'house']" /></li>
          <li class="menu_list_item menu_list_item_active" v-if="page == 'senate'"><font-awesome-icon icon="fa-solid fa-building-columns" /></li>
          <li class="menu_list_item" v-else @click="page = 'senate'"><font-awesome-icon icon="fa-solid fa-building-columns" /></li>
          <li class="menu_list_item menu_list_item_active" v-if="page == 'parties'"><font-awesome-icon icon="fa-solid fa-flag" /></li>
          <li class="menu_list_item" v-else @click="page = 'parties'"><font-awesome-icon icon="fa-solid fa-flag" /></li>
          <li class="menu_list_item menu_list_item_active" v-if="page == 'laws'"><font-awesome-icon icon="fa-solid fa-book" /></li>
          <li class="menu_list_item" v-else @click="page = 'laws'"><font-awesome-icon icon="fa-solid fa-book" /></li>
        </ul>
        <ul class="menu_list" v-else>
          <li class="menu_list_item menu_list_item_active" v-if="page == 'home'"><font-awesome-icon :icon="['fas', 'house']"/></li>
          <li class="menu_list_item" v-else @click="page = 'home'"><font-awesome-icon :icon="['fas', 'house']" /></li>
          <li class="menu_list_item menu_list_item_active" v-if="page == 'laws'"><font-awesome-icon icon="fa-solid fa-book" /></li>
          <li class="menu_list_item" v-else @click="page = 'laws'"><font-awesome-icon icon="fa-solid fa-book" /></li>
        </ul>
      </div>
      <div class="main_display">
        <div class="home_page" v-if="page == 'home'">
          <div class="home_header">
            <div>Los Santos - Senate</div>
            <div class="home_header_buttons">
              <div>Wellcome: {{ player.first_name }} {{ player.last_name }}</div>
              <button>Exit</button>
            </div>
          </div>
          <div class="home_body">
            <h2>Senate Overview</h2>
            <div class="chart_container">
              <parliamentChart :imported_data="toPartyChartData()"></parliamentChart>
              <pieChart :imported_data="calculatePie()"></pieChart>
            </div>
          </div>
        </div>
        <senatePage v-if="page == 'senate'" class="senate_page" :player="player" :parties="parties"></senatePage>
        <partiesPage @createParty="createParty" @changeRoles="changeRoles" @joinParty="joinParty" @leaveParty="leaveParty" v-if="page == 'parties'" class="parties_page" :player="player" :parties="parties" :party="getPlayerParty()" :leadership="generateLeadership()"></partiesPage>
        <lawsPage :laws="laws" class="laws_page" v-if="page == 'laws'"></lawsPage>
      </div>
    </div>
  </main>
</template>
