# Create  nested routed routes in React Router
# Use URL parameters in React Router
# Use the useRouteMatch and useParams hooks to access informaiton about React Router's internal state


- Linking to the Individial Movie Page
    To start, let's create out MovieShow component. Later on we will see that this component will need to dynamically figure out which movie it should render. 
We'll import  MovieShow into MoviesPage file to display the MovieShow container if the route matches /movies/:movieId. We also need to import the useRouteMatch hook from React Router, which we'll use to identify the matched route. 

import React from "react";
import { Route, useRouteMatch } from "react-router-dom";
impor MovieShow from "./MovieShow";


function MoviesPage( { movies } ) {
    <div>
        <MovieList movies={movies} />
        <Route path={`${match.url}/:movieId`}>
            <MovieShow />
        </Route>
    </div>
    );
}

export default Movies Page;

## Handling what happends if we only visit the first Route
In the top-level component (App.js in this case), create our "parent" routes and render <MoviesPage>
In MoviesPage.js, render <MoviesList>
In MoviesList.js, iterate through the movies object and create a dynamic Link for each movie using its id
Back in MoviesPage.js, import useRouteMatch and create the child route by combining the current url with the :movie_id parameter; inside the child route, render <MovieShow>, passing the movies object as props
In MovieShow.js, import useParams; use the :movie_id from the params object to access the correct movie from the movies object and display it on the page