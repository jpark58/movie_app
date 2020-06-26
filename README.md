# Creating movie recommendation app

## Use API from yts.am

However, since YTS keeps changing their URL, so we will use a serverless function to proxy the requests to it.  
We will use id, year, title, summary, and poster.  
[Link]:https://yts-proxy.now.sh/list_movies.json

---

## componentDidMount()

Use axios to fetch data.

```
npm i axios
```

axios takes a little bit of time. So we add async and await to getMoviews function

```
getMovies = async () => {
    const movies = await axios.get("https://yts-proxy.now.sh/list_movies.json");
  };
  async componentDidMount() {
    this.getMovies();
  }
```

---

## Deploying on github pages

Run below command to set up environment.

```
npm i gh-pages
```

Modify package.json. Add followings:

```
"scripts": {
    "deploy": "gh-pages -d build",
    "predeploy": "npm run build"
  },

"homepage": "https://jpark58.github.io/movie_app/"
```
