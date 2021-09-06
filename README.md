# Frontend Challenge

The purpose of this challenge is to evaluate your knowledge in the domain of front-end development. We expect you to build an Entities search application using AYLIEN News API. We are looking for a readable, easy-to-understand code that follows best practices and design patterns.

## The challenge
We need you to develop a Client (UI) architecture that allows users to search among entities and see related stories at the bottom of the search bar.

### Terminology
- An entity is a thing with a distinct and independent existence.
- A story contains information about a news article enriched with NLP metadata.

### Description
For this project, you will provide a search bar that allows users to search via entities using the `/autocomplete` endpoint and display related stories using the `/stories` endpoint.

We :heart: React and we already created a boilerplate project using [Create React App](https://create-react-app.dev/). Feel free to add any extra depencency that normally would be necessary or would make an engineers life easier. The prototype is just a suggestion — you have complete creative freedom!


## Required problems to resolve:
  1. Webpack configuration that will deal with CORS issue while calling news-api.
  2. Deliver code meeting acceptance criteria from the challange.
  3. Make the design responsive so it'll render properly also on mobile devices.
  4. Deliver unit tests covering critical logic of the project.
  5. Bonus: Deliver e2e tests using Cypress.

### AC:
  * Application home page contains a search bar that let's a user type text in it (look at the simple design below).
  * Once text is provided into search bar, it'll fetch autocomplete results and present them in a selectable dropdown.
  * Selected entity from a dropdown replace provided text in the search bar.
  * Clicking search button fetch stories using news-api with provided entity in the search bar.
  * Fetched data is presented as a list of stories below the search bar (look at the simple desing below).
  * Whole application should run without any errors following happy.
  * Documentation provided in the readme should be sufficient to run the application locally on a PC.

<p align="center">
  <img src="https://github.com/AYLIEN/frontend-challenge/blob/master/prototype.png?raw=true">
</p>

## API
For using API, In order to access API you have to register for the News API and follow the following documentations:

Registration form for the News API service: https://newsapi.aylien.com/signup

Documentation of the autocompletes endpoint: https://docs.aylien.com/newsapi/endpoints/#autocompletes
Example request using axios: 
```
axios.get('https://api.aylien.com/news/autocompletes', {
headers: {
    'Content-Type': 'application/json',
'X-AYLIEN-NewsAPI-Application-ID': 'f562734b',
'X-AYLIEN-NewsAPI-Application-Key': '242d78e610884df2e931d0d94a99446a',
},
params: {
    type: 'dbpedia_resources',
    term: 'Tesla',
    language: 'en',
    perPage: 3,
}
})
.then(function (response) {
console.log('response', response);
})
.catch(function (error) {console.log(error)})
```

Documentation of the stories endpoint: https://docs.aylien.com/newsapi/endpoints/#stories

Example request using axios:
```
axios.get('https://api.aylien.com/news/stories', {
headers: {
    'Content-Type': 'application/json',
'X-AYLIEN-NewsAPI-Application-ID': 'f562734b',
'X-AYLIEN-NewsAPI-Application-Key': '242d78e610884df2e931d0d94a99446a',
},
params: {
    language: ['en'],
    perPage: 25,
    cursor: '*',
    "entities.surface_forms.text": ["Nikola Tesla"]
}
})
.then(function (response) {
console.log('response', response);
})
.catch(function (error) {console.log(error)})
```

Calling the API: https://docs.aylien.com/newsapi/#calling-the-api

Using our Swagger definition with Postman (optional): https://docs.aylien.com/newsapi/#testing-the-news-api-with-postman

## Notes
Before starting the challenge, we would also like you to identify the required steps and provide a time estimate for these and share with us by email. If you can split these tasks into smaller items, please also share these. Keep in mind that of course we expect a meaningful contribution (around 4 hours) but it’s up to you how much time you invest. Also it should be possible to review your solution in a reasonable amount of time, so please provide instructions on how to get up and running with your solution and test it. Your solution is expected as a zip file, but please also include your .git directory — we are interested in your development steps, not just the end result.

We forged this exercise with great care and enthusiasm. Even if you decide not to submit your solution, we would appreciate your feedback. What was the most enjoyable part? What was unreasonably annoying? Let us know so that we can improve.
