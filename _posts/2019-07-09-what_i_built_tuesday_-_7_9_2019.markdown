---
layout: post
title:      "What I Built Tuesday - 7/9/2019"
date:       2019-07-10 00:38:32 +0000
permalink:  what_i_built_tuesday_-_7_9_2019
---


For this week, I added in a few more components to my Movie-TV-Hub application. One of the components I added was the Now Playing component. This component utilized the Gallery component and displayed a gallery of movies that are currently playing in the theater.

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

Another component I addded was the Movie TV Details component. This component display information about a movie or tv show. At the moment, it only conatains hard coded data. As I started to work with The Movie Database API, I will update this component to display information it receives from the API. 

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

For next week, I will add in the fetch request method to some of the components - e.g. Popular Movie component - to make request to The Movie Database API and display information it receives from the API. 
