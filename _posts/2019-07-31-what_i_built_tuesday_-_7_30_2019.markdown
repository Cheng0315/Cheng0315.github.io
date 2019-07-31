---
layout: post
title:      "What I built Tuesday - 7/30/2019"
date:       2019-07-31 05:52:29 +0000
permalink:  what_i_built_tuesday_-_7_30_2019
---


For this week his week, I added in more actions to my application. The upcoming movies action, for example, make a request to The Movie Database API, return a list of upcoming movies and update the state of the application.

```
const fetchUpcomingMovies = () => dispatch => {
  dispatch({type: 'START_ADDING_MOVIES'});
  fetch('/movie/upcoming')
    .then(response => response.json())
    .then(moviesData => 
      dispatch({
        type: 'FETCH_UPCOMING_MOVIES',
        payload: moviesData
    }))
    .catch(error => console.log(error))
}

export default fetchUpcomingMovies;
```

In addition to adding actions to my application, I also added in the latest tv shows component, detailed below. This component displayed a gallery of the latest tv shows. 

```
import React from 'react'
import Gallery from './gallery'
 
class LatestTvShows extends React.Component {
  render() {
    return (
      <div>
        <p>Now Playing</p>
        <Gallery array={Array(7)}/>
      </div>
    )
  }
}

export default LatestTvShows;
```

For next week, I would like to add in components such as now airing tv shows and popular tv shows.
