---
layout: post
title:      "What I built Tuesday - 7/16/2019"
date:       2019-07-16 22:01:11 -0400
permalink:  what_i_built_tuesday_-_7_16_2019
---


This week, I added the fetchPopularMovies action to my application. This action makes a request to The Movies Database API and return the data of the current popular movies. 

```
const fetchPopularMovies = () => dispatch => {
  dispatch({type: 'START_ADDING_MOVIES'});
  fetch('/movie/popular')
    .then(response => response.json())
    .then(moviesData => 
      dispatch({
        type: 'FETCH_POPULAR_MOVIES',
        payload: moviesData
    }))
    .catch(error => console.log(error))
}

export default fetchPopularMovies;
```

The goal for next week is to add in redux to manage the states of the application.
