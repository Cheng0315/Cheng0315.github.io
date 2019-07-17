---
layout: post
title:      "What I Built Tuesday - 7/2/2019"
date:       2019-07-02 23:58:00 -0400
permalink:  what_i_built_tuesday_-_7_2_2019
---


One of the things I love about React is the ability use code that other people had already written. For this week, I added in the carousel component and the gallery component to my application. First, I install the react-responsive-carousel component. 

``
npm install react-responsive-carousel --save
``

Then I added in the carousel component file and inside the file I added in the code.

```
import React, { Component } from 'react';
import "react-responsive-carousel/lib/styles/carousel.min.css";
import { Carousel } from 'react-responsive-carousel';
import '../carousel.css'
 
class MovieCarousel extends Component {
  render() {
    return (
      <Carousel className='movie-carousel' infiniteLoop={true} autoPlay={true} interval={3000} showThumbs={false} stopOnHover={false}>
        <div>
          <img src="image-1" />
        </div>
        <div>
          <img src="image-2" />
        </div>
        <div>
          <img src="image-3" />
        </div>
      </Carousel>
    );
  }
};

export default MovieCarousel;
```

After that, I added the gallery component and added in the code.

```
import React from 'react'
import AliceCarousel from 'react-alice-carousel'
import 'react-alice-carousel/lib/alice-carousel.css'
 
class Gallery extends React.Component {
  state = {
    currentIndex: 0,
    itemsInSlide: 1,
    responsive: { 0: { items: 3 }},
    galleryItems: this.galleryItems(),
  }
 
  galleryItems() {
    return (
      this.props.array.fill().map((item, i) => <h2 className="item">{i + 1}</h2>)
    )
  }
 
  slidePrevPage = () => {
    const currentIndex = this.state.currentIndex - this.state.itemsInSlide
    this.setState({ currentIndex })
  }
 
  slideNextPage = () => {
    const { itemsInSlide, galleryItems: { length }} = this.state
    let currentIndex = this.state.currentIndex + itemsInSlide
    if (currentIndex > length) currentIndex = length
 
    this.setState({ currentIndex })
  }
 
  handleOnSlideChange = (event) => {
    const { itemsInSlide, item } = event
    this.setState({ itemsInSlide, currentIndex: item })
  }
 
  render() {
    const { currentIndex, galleryItems, responsive } = this.state
 
    return (
      <div>
        <AliceCarousel
          items={galleryItems}
          slideToIndex={currentIndex}
          responsive={responsive}
          onInitialized={this.handleOnSlideChange}
          onSlideChanged={this.handleOnSlideChange}
          onResized={this.handleOnSlideChange}
        />
        <button onClick={this.slidePrevPage}>Prev Page</button>
        <button onClick={this.slideNextPage}>Next Page</button>
      </div>
    )
  }
}

export default Gallery;
```

With that, I was able to create the carousel and the gallery component that I needed. The goal for next week is to add in conponents such as popular movies and now playing movies. These components will display a gallery of movies in terms of what they represent. E.g. the popular movies component will display a gallery of movies that are popular at the moment while the now playing movies component will display a gallery of movies that are now playing in theater.
