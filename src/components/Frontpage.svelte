<link
      rel="stylesheet"
      href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@48,400,0,0"
    />

<main>
    <div class="intro">
      <div>
        <h1>Full Stack Development with NodeJS</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nihil
          maxime repellat non officiis saepe, id quia, soluta adipisci
          excepturi possimus voluptates, doloremque mollitia? Doloribus nihil
          fugiat nam quam reiciendis provident.
        </p>
        <div class="buttons-container"></div>
      </div>
    </div>

    <div class="welcome-container">
      <div>
        <p class="subtitle">Free service</p>
        <span class="material-symbols-outlined"> payments </span>
        <p class="lorem">
          Lorem ipsum dolor sit amet consectetur adipisicing. Lorem ipsum dolor sit amet.
        </p>
      </div>
      <div>
        <p class="subtitle">Good learning outcome</p>
        <span class="material-symbols-outlined"> school </span>
        <p class="lorem">
          Lorem ipsum dolor sit amet consectetur adipisicing. Lorem ipsum dolor sit amet.
        </p>
      </div>
      <div>
        <p class="subtitle">Fun and easy learning</p>
        <span class="material-symbols-outlined"> celebration </span>
        <p class="lorem">
          Lorem ipsum dolor sit amet, consectetur adipisicing. Lorem ipsum dolor sit amet.
        </p>
      </div>
    </div>
    <div class="coding-examples-container"></div>
  </main>


  <style>
.intro {
  height: 50vh;
  width: 100%;
  background-color: #252020;
  display: flex;
  align-items: center;
}

.intro div {
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-direction: column;
  margin: 0 20em;
}
.intro div p {
  color: grey;
  text-align: center;
  font-size: 15px;
}
.intro div h1 {
  color: white;
}

.pages-container {
  text-align: center;
  margin: 20px 0 0 0;
  color: #252020;
}

.welcome-container {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  align-items: center;
  height: 40vh;
}

.welcome-container div {
  width: 30vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.welcome-container div .subtitle {
  font-weight: 900;
}
.welcome-container div .lorem {
  font-size: 11px;
  text-align: center;
}

.welcome-container div span {
  font-size: 55px;
}
  </style>