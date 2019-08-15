---
layout: post
title:      "What I Built Tuesday - 8/13/2019"
date:       2019-08-15 14:10:35 +0000
permalink:  what_i_built_tuesday_-_8_13_2019
---


I added the airingTodayTvShows action, topRatedTvShows action, and onTheAirTvShows action to my Movie-Tv-Hub application this week. In addition, I updated the movieTvReducer to check for tv shows cases, detailed below.

```
const initialState = {
  loadingMovies: false,
  popularMovies: [],
  nowPlayingMovies: [],
  topRatedMovies: [],
  upcomingMovies: [],
  topRatedTvShows: [],
  latestTvShows: [],
  airingTodayTvShows: [],
  onAirTvShows: [],
  popularTvShows: []
}

export default function plateReducer(state = initialState, action) {
  switch(action.type){
    case 'START_ADDING_MOVIES':
      return {...state, loadingMovies: true}
    case 'FETCH_NOW_PLAYING_MOVIES':
      return {...state, loadingMovies: false, nowPlayingMovies: action.payload}
    case 'FETCH_POPULAR_MOVIES':
      return {...state, loadingMovies: false, popularMovies: action.payload}
    case 'FETCH_TOP_RATED_MOVIES':
      return {...state, loadingMovies: false, topRatedMovies: action.payload}
    case 'FETCH_UPCOMING_MOVIES':
      return {...state, loadingMovies: false, upcomingMovies: action.payload}
    case 'FETCH_TOP_RATED_TV_SHOWS':
      return {...state, loadingMovies: false, topRatedTvShows: action.payload}
    case 'FETCH_POPULAR_TV_SHOWS':
      return {...state, loadingMovies: false, popularTvShows: action.payload}
    case 'FETCH_ON_AIR_TV_SHOWS':
      return {...state, loadingMovies: false, onAirTvShows: action.payload}
    case 'FETCH_AIRING_TODAY_TV_SHOWS':
      return {...state, loadingMovies: false, airingTodayTvShows: action.payload}
    case 'FETCH_TOP_RATED_TV_SHOWS':
      return {...state, loadingMovies: false, topRatedTvShows: action.payload}
    default: 
      return state
  }
}
```

Next week, I would like to import the tv show components to the app component and display them along with the movies component.
