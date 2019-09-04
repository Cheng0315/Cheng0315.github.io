---
layout: post
title:      "What I Built Tuesday - 9/3/2019"
date:       2019-09-04 08:05:09 +0000
permalink:  what_i_built_tuesday_-_9_3_2019
---


This week, I added the movie and tv containers to my Movie-Tv-Hub application. The two containers help organized the many movie and tv components that I have and make it easier for me to import components that belong together. Details about the components are shown below.

Movie container

```
import React from 'react'
import MovieCarousel from '../components/carousel'
import PopularMovies from '../components/popularMovies'
import UpcomingMovies from '../components/upcomingMovies'
import TopRatedMovies from '../components/topRatedMovies'
import NowPlayingMovies from '../components/nowPlayingMovies'
 
class MoviesContainer extends React.Component {
  render() {
    return (
      <div>
        <MovieCarousel/>
        <NowPlayingMovies/>
        <PopularMovies/>
        <UpcomingMovies/>
        <TopRatedMovies/>
      </div>
    )
  }
}

export default MoviesContainer;
```

Tv Container

```
import React from 'react'
import LatestTvShows from '../components/latestTvShows'
import OnTheAirTvShows from '../components/onTheAirTvShows'
import PopularTvShows from '../components/popularTvShows'
import TopRatedTvShows from '../components/topRatedTvShows'
 
class TvContainer extends React.Component {
  render() {
    return (
      <div>
        <PopularTvShows/>
        <TopRatedTvShows/>
        <OnTheAirTvShows/>
        <LatestTvShows/>
      </div>
    )
  }
}

export default TvContainer;
```


