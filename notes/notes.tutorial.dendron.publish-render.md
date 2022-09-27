---
id: 82gGgw5zpqWI2jl8iVWbD
title: Publish Render
desc: ''
updated: 1642549159551
created: 1641257083979
---
# Publish my Dendron vault using Render

Publish my Dendron vault by deploying on [Render](https://render.com/), with notes stored on private GitHub repo.

Credit to the [[Netlify workflow|notes.tutorial.dendron.publish-netlify]].

Why Render when [[Netlify workflow|notes.tutorial.dendron.publish-netlify]] is already good enough?
- simply because of the generous limit of free plan in Render is [400 build-hour](https://render.com/docs/build-limits) vs [300 build minutes](https://www.netlify.com/pricing/) of Netlify 

## Getting started

1. Signup [Render](https://render.com/)

2. Create new `Static site`
    ![create-static-site](https://i.imgur.com/RgjHQFn.jpg){max-width: 300px, display: block, margin: 0 auto}
    
3. Import my repo `h7b-dendron-netlify` to Render
    ![render-import](https://i.imgur.com/nvodACW.jpg){max-width: 300px, display: block, margin: 0 auto}

4. Configure deploy settings
    ![render-deploy-config](https://i.imgur.com/ZUZr838.jpg){max-width: 300px, display: block, margin: 0 auto}
    
    Name: 
    ```shell
    dendron
    ```
    the url of published site will be: https://dendron.onrender.com  
    
    Build Command: 
    ```shell 
    rm -rf .next; rm -rf docs; rm -rf node_modules; npm install @dendronhq/dendron-cli@latest; npx dendron publish init; npx dendron publish export; mv .next/out docs
    ```
    Publish directory:
    ```shell
    ./docs
    ```

DONE