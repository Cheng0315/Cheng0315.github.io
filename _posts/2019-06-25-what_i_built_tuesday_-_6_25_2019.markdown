---
layout: post
title:      "What I Built Tuesday - 6/25/2019"
date:       2019-06-25 08:08:06 +0000
permalink:  what_i_built_tuesday_-_6_25_2019
---


Hi there! Thank you for taking the time to read this blog post! In this blog post series - What I Built Tuesday -  I will talk about what I build each week in regard to building an application that displays information about movies and tv shows. This application will use React as the front-end and will use "The Movie Database API" as the source to retrieve data and information about movies and tv shows to display to the users. This application will also have feature such as letting users rate movies and tv shows if they have a TMDB (The Movie Database) account.

To start this project, I used the create-react-app command to create a new react app, as shown below.

``
npx create-react-app movie-tv-hub
``

This command created a directory called movie-tv-hub, and inside the movie-tv-hub directory are the project structure and dependencies, which are already set up when we used the command above. Then I used the command line to moved into the root of the movie-tv-hub directory and delete some of the code inside the App.js file.

From
```
import React from 'react';
import logo from './logo.svg';
import './App.css';

 function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

 export default App;
```

To 
```
import React from 'react';
import logo from './logo.svg';
import './App.css';

 function App() {
  return (
    <div className="App">
		
    </div>
  );
}

export default App;
```

After that, I created a components directory inside the src directory and inside the components directory I created a navBar.js file. Because I am comfortable using the react-bootstrap framework, I wanted to use a different front-end framework for this project. I decided to go with Material-UI. 

First, I installed the Material-UI framework using this command.

``
npm install @material-ui/core@next
``

Then I installed the Material-UI icons using the following command.

``
npm install @material-ui/icons
``

Then I added in the code for the navigation bar to my navBar.js file.

```
export default function NavBar() {
  return (
    <nav className={classes.grow}>
      <AppBar position="static">
        <Toolbar>
          <Typography className={classes.title} variant="h6" noWrap>
            Movie TV Hub
          </Typography>
          <div className={classes.search}>
            <div className={classes.searchIcon}>
              <SearchIcon />
            </div>
            <InputBase
              placeholder="Search…"
              classes={{
                root: classes.inputRoot,
                input: classes.inputInput,
              }}
              inputProps={{ 'aria-label': 'Search' }}
            />
          </div>
          <div className={classes.grow} />
          <div className={classes.sectionDesktop}>
            <IconButton
              edge="end"
              aria-label="Account of current user"
              aria-controls={menuId}
              aria-haspopup="true"
              onClick={handleProfileMenuOpen}
              color="inherit"
            >
              <AccountCircle />
            </IconButton>
          </div>
          <div className={classes.sectionMobile}>
            <IconButton
              aria-label="Show more"
              aria-controls={mobileMenuId}
              aria-haspopup="true"
              onClick={handleMobileMenuOpen}
              color="inherit"
            >
              <MoreIcon />
            </IconButton>
          </div>
        </Toolbar>
      </AppBar>
      {renderMobileMenu}
      {renderMenu}
    </nav>
  );
}
```

In App.js file, I imported the navBar component and added it to the return value inside the app function.

```
import React from 'react';
import './App.css';
import NavBar from './components/navBar'
import MovieCarousel from './components/carousel'

function App() {
  return (
    <div className="App">
      <NavBar/>
    </div>
  );
}

export default App;
```

And that was what I was able to get to this week. My goal for next week is to add in a carousel that displays images . This carousel will be used for displaying image of movies when when I start making request to The Movie Database API.


