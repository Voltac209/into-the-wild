<h3>Table of Contents</h3>
<ul>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#overview">Overview</a></li>
    <li><a href="#highlights">Highlights</a></li>
    <li><a href="#implementation">Implementation</a></li>
    <li><a href="#installation-and-setup">Installation and Setup</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#future-work">Future Work</a></li>
</ul>

<h3 id="introduction">Introduction</h3>
<div>
   Into the Wild is a frontend project that simulates a wildlife tracking experience through species search and interactive map exploration. The project is designed to showcase component-driven UI development, map integration, and real-time state synchronization in Vue 3.
</div>

<h3 id="overview">Overview</h3>
<div>
   Users can search from 25+ animal species, add animals to a shortlist, and update the map view based on the selected species. The application combines a searchable interface with live map interaction to present the project as a polished, portfolio-ready frontend build.
</div>

<h3 id="highlights">Highlights</h3>
<ul>
   <li>Built to demonstrate frontend engineering with Vue 3, JavaScript, and Tailwind CSS.</li>
   <li>Implemented species-based search and filtering for a curated dataset of 25+ animals.</li>
   <li>Integrated Google Maps to update the displayed location marker based on user selection.</li>
   <li>Designed a custom reactive <code>EventBus</code> to coordinate state between independent Vue components.</li>
</ul>

<h3 id="implementation">Implementation</h3>
<div>
   I developed this <b>responsive web application</b> using <b>Vue 3</b>, <b>JavaScript</b>, and <b>Tailwind CSS</b>.
   <br><br>
   The interface is split into focused Vue components for search and map rendering. I used a custom reactive <code>EventBus</code> to synchronize animal selection with the map view, allowing the displayed marker position to update as the selected animal changes.
   <br><br>
   Google Maps is integrated through the <b>Google Maps API</b> and the <b>vue3-google-map</b> package, giving users an interactive map with live location updates based on their selected species.
</div>

<h3 id="installation-and-setup">Installation and Setup</h3>
<blockquote>
   In order to run the application, you will need an API Key for Google Maps integration. If you do not have one already, you can request it from Google Maps Platform by visiting the following link: <br><a href="https://console.cloud.google.com/google/maps-apis/overview">https://console.cloud.google.com/google/maps-apis/overview</a>.
</blockquote>
<br>
<ul>
   <li>
      Clone the git repo using the following: <code>git clone https://github.com/Voltac209/into-the-wild.git</code>
   </li>
   <li>
      Navigate to <code>into-the-wild</code> folder and install the required dependencies by running <code>npm install</code>.
   </li>
   <li>
      Create <code>.env</code> file in the <code>into-the-wild</code> folder and define the variable <code>VUE_APP_API_KEY</code> to store the API KEY for Google Maps integration. Execute <code>npm run serve</code> to start the development server.
   </li>
   <li>Navigate to <code>http://localhost:8080</code> to access the application</li>
</ul>

<h3 id="usage">Usage</h3>
<div>
   Please feel free to explore the website using the following link: <a href="https://into-the-wild.onrender.com/">into-the-wild.onrender.com</a>
</div>
<br>
<div>
   Welcome to the Homepage! In the top-left corner, you will find a search box waiting for your input. Begin typing and the app will display possible selections in a dropdown menu. These selections are currently retrieved from the list of 25 animals provided below. Once you have found your desired animal, click on the entry in the dropdown to populate the search input followed with hitting the search button to proceed to the next step.
</div>
<br>

```javascript
animalList = ["Royal Bengal Tiger", "Asian Elephant", "Spotted Deer", "Sambar Deer", "Gharial", "Boar", "Chital", "Pangolin", "Langur", "Goral", "Himalayan Black Bear", "Indian Grey Mongoose", "Leopard", "Cheetah", "Wolf", "Bison", "Nilgai", "Hog Deer", "Crocodile", "Black Panther", "Jackal", "Jaguar", "Sloth", "Fox", "Indian Hare"]
```

<br>
<img src="./images/home-page.png"><br>
<br>
<div>
   Upon clicking the search button, your desired animal joins a list located to the left of the map. Made a mistake? No problem. Use the cross button positioned next to the animal's name to remove it from the list.
</div>
<br><br>
<img src="./images/home-page-with-list.png">
<br><br>
<div>
   Choose an animal from the list. Upon selection, the map will locate the animal you selected on the map.
</div>
<br><br>
<img src="./images/locating-animal.png">
<br>

<h3 id="future-work">Future Work</h3>
<ul>
   <li>
      <b>Waiting Queue Approach</b>: tracking the number of individuals eager to observe the wildlife and monitoring the current occupancy at specific locations is vital for preserving the ambience of these natural ecosystems.
   </li>
   <li>
      <b>Marker Clusters</b>: highlight the presence of fauna using cluster of markers based on the user's location.
   </li>
   <li>
      <b>Centralized Server and Fog Computing</b>: levergaing a central server to store animal locations and securely dispatch them to connected devices, resulting in a notable reduction in both latency and overhead.
   </li>
</ul>

<hr>
<div>
    This repository represents a solo project build. If you have enhancement requests or encounter a bug, please report it in the <a href="https://github.com/Voltac209/into-the-wild/issues">Issues</a> section.
</div>
