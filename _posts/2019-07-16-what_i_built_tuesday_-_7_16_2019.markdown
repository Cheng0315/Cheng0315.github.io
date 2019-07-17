---
layout: post
title:      "What I built Tuesday - 7/16/2019"
date:       2019-07-17 02:01:10 +0000
permalink:  what_i_built_tuesday_-_7_16_2019
---


For this week, I added in the fetch method to the popular movies component. This method make a request to The Movies Database API and return the data of the current popular movies. 

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

The goals for next week are to use these data and display them in the popular movies component.
