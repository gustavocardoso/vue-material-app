<template>
  <div id="app">
    <md-card mdWithHover="true">
      <md-card-header>
        <div class="md-title">Vue Material App</div>
        <div class="md-subhead">By codingthesmartway.com</div>
      </md-card-header>

      <md-card-content>
        <md-button class="md-raised md-primary" v-on:click.native="fillTable()">Fill table</md-button>
        <md-button class="md-raised md-primary" v-on:click.native="clearTable()">Clear</md-button>
      </md-card-content>

      <md-table>
        <md-table-header>
          <md-table-row>
            <md-table-head>First name</md-table-head>
            <md-table-head>Last name</md-table-head>
            <md-table-head>E-mail</md-table-head>
          </md-table-row>
        </md-table-header>

        <md-table-body>
          <md-table-row v-for="contact in contacts" :key="contact.id">
            <md-table-cell>{{ contact.firstname }}</md-table-cell>
            <md-table-cell>{{ contact.lastname }}</md-table-cell>
            <md-table-cell>{{ contact.email }}</md-table-cell>
          </md-table-row>
        </md-table-body>
      </md-table>
    </md-card>
  </div>
</template>

<script>
  export default {
    name: 'app',

    data() {
      return {
        contacts: []
      }
    },

    methods: {
      fillTable: function() {
        this.contacts.push({ id: 1, firstname: 'Gustavo', lastname: 'Cardoso', email: 'gustavocardoso@gmail.com' })
        this.contacts.push({ id: 1, firstname: 'Rosele', lastname: 'Martins', email: 'martins.rosele@gmail.com' })
        this.contacts.push({ id: 1, firstname: 'Olívia', lastname: 'Martins Faria', email: 'oliviafaria@gmail.com' })
      },

      clearTable: function() {
        this.contacts.splice(0, this.contacts.length)
      }
    }
  }
</script>

<style>
  #app {
    padding: 30px;
  }
</style>
