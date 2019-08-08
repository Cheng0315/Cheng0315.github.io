---
layout: post
title:      "What I Built Tuesday - 8/7/2019"
date:       2019-08-08 01:23:37 +0000
permalink:  what_i_built_tuesday_-_8_7_2019
---


After adding in the components and actions for the movie galleries in my application, I added in the components and actions for the tv show galleries. 

```
import React from 'react'
import Gallery from './gallery'
 
class PopularTvShows extends React.Component {
  render() {
    return (
      <div>
        <p>Popular>
        <Gallery array={Array(7)}/>
      </div>
    )
  }
}

export default PopularTvShows;
```

The component above displays a gallery of popular tv shows. The action for that component is detailed below.

```
const fetchPopularTvSHows = () => dispatch => {
  dispatch({type: 'START_ADDING_MOVIES'});
  fetch('/tv/popular')
    .then(response => response.json())
    .then(moviesData => 
      dispatch({
        type: 'FETCH_POPULAR_TV_SHOWS',
        payload: moviesData
    }))
    .catch(error => console.log(error))
}

export default fetchPopularTvShows;
```

The goals for next week are to add more cases to the reducer to update the state of the tv shows.
