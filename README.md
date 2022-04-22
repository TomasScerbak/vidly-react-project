# vidly-react-project

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- see simple table of movies which mimicks shopping list. User should see number of movies in the list and also be able to remove any item from the list.

### Links

- Solution URL: [https://github.com/TomasScerbak/airbnb-react-project.git]
- Live Site URL: [https://tomasscerbak.github.io/airbnb-react-project/]

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Bootstrap
- React JS

### What I learned

-creating component
-specifying children
-empedding expressions
-setting attributes
-rendering classes dynamically
-rendering lists
-conditional rendering
-handling events
-binding handling event

```js
import React, { Component } from 'react';
import { getMovies } from '../services/fakeMovieService'

class Movies extends Component {
    state = { 
        movies: getMovies()
     };

     handleDelete = movie => {
        const movies = this.state.movies.filter(m => m._id !== movie._id);
        this.setState({movies})
     }
    render() { 

        const { length: count } = this.state.movies;

        if (count === 0) 
        return <p>There are no movies in the database</p>;

        return (
            <React.Fragment>
            <p>Showing {count} movies</p>
            <table className='table'>
                <thead>
                    <tr>
                        <th>Title</th>
                        <th>Genre</th>
                        <th>Stock</th>
                        <th>Rate</th>
                        <th></th>
                    </tr>
                </thead>
                <tbody>
                    { this.state.movies.map(movie => (
                    <tr key={movie._id}>
                        <td>{movie.title}</td>
                        <td>{movie.genre.name}</td>
                        <td>{movie.numberInStock}</td>
                        <td>{movie.dailyRentalRate}</td>
                        <td><button onClick={() => this.handleDelete(movie)} className='btn btn-danger btn-sm'>Delete</button></td>
                    </tr>))}
                </tbody>
            </table>
            </React.Fragment>
        );
    }
}
 
export default Movies;
```

### Continued development

I will continue to use REACT and build REACT projects for further developement.


## Author

- Website - [Tomas Scerbak](https://tomasscerbak.github.io/tomas-scerbak-portfolio/)
- Frontend Mentor - [@Potato](https://www.frontendmentor.io/profile/TomasScerbak)
