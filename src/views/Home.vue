<template>
  <div id="tabs" class="container">
  <div class="tabs">
      <a v-on:click="activetab='1'" v-bind:class="[ activetab === '1' ? 'active' : '' ]">France</a>
      <a v-on:click="activetab='2'" v-bind:class="[ activetab === '2' ? 'active' : '' ]">Spain</a>
      <a v-on:click="activetab='3'" v-bind:class="[ activetab === '3' ? 'active' : '' ]">Germany           </a>
      <a v-on:click="activetab='4'" v-bind:class="[ activetab === '4' ? 'active' : '' ]">Italy</a>
  </div>
  <div class="content">
      <div v-if="activetab ==='1'" class="tabcontent">
          <table>
            <tr><td class="legend">Area:</td><td class="data">640,679 km<sup>2</sup></td><td rowspan="5"><img class="map" src="https://drive.google.com/thumbnail?id=1edVL631_KOzd5zXzwrDNbn7bZDxqcRUQ"></td></tr>
            <tr><td class="legend">Population:</td><td class="data">67 million</td></tr>
            <tr><td class="legend">Capital:</td><td class="data">Paris</td></tr>
            <tr><td class="legend">Language:</td><td class="data">French</td></tr>
            <tr><td class="legend" valign="top">Flag:</td><td class="data"><img class="flag" src="https://upload.wikimedia.org/wikipedia/en/thumb/c/c3/Flag_of_France.svg/900px-Flag_of_France.svg.png" width="80"></td></tr>
          </table>
      </div>
      <div v-if="activetab ==='2'" class="tabcontent">
          <table>
            <tr><td class="legend">Area:</td><td class="data">505,990 km<sup>2</sup></td><td rowspan="5"><img class="map" src="https://drive.google.com/thumbnail?id=1AlVDaA3-wXNhqtXkfWoI3tD5cxZNfJu1"></td></tr>
            <tr><td class="legend">Population:</td><td class="data">47 million</td></tr>
            <tr><td class="legend">Capital:</td><td class="data">Madrid</td></tr>
            <tr><td class="legend">Language:</td><td class="data">Spanish</td></tr>
            <tr><td class="legend" valign="top">Flag:</td><td class="data"><img class="flag" src="https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/Flag_of_Spain.svg/750px-Flag_of_Spain.svg.png" width="80"></td></tr>
          </table>
      </div>
      <div v-if="activetab ==='3'" class="tabcontent">
          <table>
            <tr><td class="legend">Area:</td><td class="data">357,386 km<sup>2</sup></td><td rowspan="5"><img class="map" src="https://drive.google.com/thumbnail?id=1JQyW1aThQxnlk3ZmogomTzhDkQGKbdC1"></td></tr>
            <tr><td class="legend">Population:</td><td class="data">83 million</td></tr>
            <tr><td class="legend">Capital:</td><td class="data">Berlin</td></tr>
            <tr><td class="legend">Language:</td><td class="data">German</td></tr>
            <tr><td class="legend" valign="top">Flag:</td><td class="data"><img class="flag" src="https://upload.wikimedia.org/wikipedia/en/thumb/b/ba/Flag_of_Germany.svg/1000px-Flag_of_Germany.svg.png" width="89"></td></tr>
          </table>
      </div>
      <div v-if="activetab ==='4'" class="tabcontent">
          <table>
            <tr><td class="legend">Area:</td><td class="data">301,340 km<sup>2</sup></td><td rowspan="5"><img class="map" src="https://drive.google.com/thumbnail?id=1_kQQJCEXyK-obQLNo5apywuWsolm3032"></td></tr>
            <tr><td class="legend">Population:</td><td class="data">60 million</td></tr>
            <tr><td class="legend">Capital:</td><td class="data">Rome</td></tr>
            <tr><td class="legend">Language:</td><td class="data">Italian</td></tr>
            <tr><td class="legend" valign="top">Flag:</td><td class="data"><img class="flag" src="https://upload.wikimedia.org/wikipedia/en/thumb/0/03/Flag_of_Italy.svg/1500px-Flag_of_Italy.svg.png" width="80"></td></tr>
          </table>
      </div>
  </div>

</div>
</template>

<script>
export default {
    name: 'Home',
    data(){
        return {
            activetab: '1'
        }
    },
    method:{

    }

}
</script>

<style scoped>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  /* color:#fff; */
}

.container {  
    max-width: 620px; 
    min-width: 420px;
    margin: 40px auto;
    font-family: "Nunito Sans", Arial, Helvetica, sans-serif;
    font-size: 0.9em;
    color: #888;
    /* background-color: #ffff; */
}

/* Style the tabs */
.tabs {
    overflow: hidden;
    margin-bottom: -2px; /* hide bottom border */
    margin-left: 24px;
    /* background-color: #ffff; */
}

.tabs a{
    float: left;
    cursor: pointer;
    padding: 12px 24px;
    transition: background-color 0.2s;
    border: 1px solid #ccc;
    border-right: none;
    background-color: #f1f1f1;
    border-radius: 10px 10px 0 0;
    font-weight: bold;
}
.tabs a:last-child { 
    border-right: 1px solid #ccc;
    /* background-color: #ffff; */
}

/* Change background color of tabs on hover */
.tabs a:hover {
    background-color: #aaa;
    color: #fff;
}

/* Styling for active tab */
.tabs a.active {
    background-color: #fff;
    color: #484848;
    border-bottom: 2px solid #fff;
    cursor: default;
}

/* Style the tab content */
.tabcontent {
    padding: 30px 50px;
    border: 1px solid #ccc;
    border-radius: 10px;
    box-shadow: 4px 4px 8px #e1e1e1;
    background-color: #ffff;
}

.tabcontent td {
  padding: 0.3em 0.4em;
  color: #484848;
  /* background-color: #ffff; */
}
.tabcontent td.legend { 
  color: #888; 
  font-weight: bold;
  text-align: right;
  /* background-color: #ffff; */
}
.tabcontent .map {
  height: 173px;
  width: 220px;
  background: #D3EAFB;
  margin-left: 60px;
  border: 1px solid #ccc;
  border-radius: 10px;
}
.data { 
  width: 120px; 
  /* background-color: white; */
}

</style>