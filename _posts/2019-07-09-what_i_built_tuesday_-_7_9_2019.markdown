---
layout: post
title:      "What I Built Tuesday - 7/9/2019"
date:       2019-07-09 20:38:33 -0400
permalink:  what_i_built_tuesday_-_7_9_2019
---


For this week, I added the nowPlaying component to my application. The component utilized the Gallery component and displayed a gallery of movies that are currently playing in the theater.

```
import React from 'react'
import Gallery from './gallery'
 
class NowPlaying extends React.Component {
  render() {
    return (
      <div>
        <p>Now Playing</p>
        <Gallery array={Array(7)}/>
      </div>
    )
  }
}

export default NowPlaying;
```

I also addded the movieTvDetails component. This component display information about a movie or tv show. At the moment, it only conatains hard coded data, but as I started to work with The Movie Database API, this component will display data it receives from the API.

```
import React from 'react'
import Gallery from './gallery'

class MovieTvDetails extends React.Component {
  render() {
    return (
      <div>
        <div>
          <h3>One Punch Man</h3>
          <img src="https://amc-theatres-res.cloudinary.com/v1553695740/amc-         cdn/production/2/movies/45800/45840/PosterDynamic/75045.jpg" />
        </div>
        <div>
          Details
          <p>
          Saitama is a hero who only became a hero for fun. After three years of “special” training, though, he’s become so   strong that he’s practically invincible. In fact, he’s too strong—even his mightiest opponents are taken out with a single punch, and it turns out that being devastatingly powerful is actually kind of a bore. With his passion for being a hero lost along with his hair, yet still faced with new enemies every day, how much longer can he keep it going?
          </p>
        </div>
        <div>
          Cast
          <Gallery array={Array(7)}/>
        </div>
        <div>
          Trailers
          <Gallery array={Array(7)}/>
        </div>
        <div>
          Reviews
         <ul>
	        <li>
					 list of reviews about the movie or tv shows
		      </li>
				 </ul>
        </div>
      </div>
    )
  }
}

export default MovieTvDetails;
```
