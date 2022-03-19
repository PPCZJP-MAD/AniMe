Original App Design Project - README Template
===

# AniMe

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
2. [Schema](#Schema)

## Overview
### Description
AniMe is a social networking app to share, discover, and interact with members of the anime watching community.


### App Evaluation
[Evaluation of your app across the following attributes]
- **Category:** Social
- **Mobile:** This app would be developed for mobile applications, but can be scaled up to a web application.
- **Story:** Profile can display favorite anime shows, following/followers count, and a currently watching list. Home screen would show followed users comments/thoughts on an anime and animes that one is following. Discovery screen displaying collection view of anime.
- **Market:** Any individual with a pre-existing or burgeoning interest in anime. There is no niche market, as the app will be accessible for any age group; however, there will be an age requirement for online safety.
- **Habit:** This app can be used as much as the user wants to keep friends and themselves updated on the animes they're following. Users would use this app less than more popular social networking apps, but could easily be used on a daily basis.
- **Scope:** The scope of AniMe is well-formed, as it establishes 3 required aspects for social networking/discovery of anime; additionally, there are optional user stories that will improve and add features to the UI. The barebones version of AniMe is still interesting to build, and the app will be technically challenging, but not impossible, to build given the time constraint.

## Product Spec

### 1. User Stories (Required and Optional)

**Required Must-have Stories**

* User can use tab-bar navigation with Home, Discover, and Profile screens.
* User can log-in.
* User can log-out
* Discovery screen that displays animes A-Z.
* Profile screen with currently watching, to watch, favorites list. 
* Home screen that displays social feed of comments/likes from their following list and following animes.



**Optional Nice-to-have Stories**

* Users can make a tier-listing of their favorite animes on their Profile screens.
* Users can sort the Discovery screen according to different filters.
* Users can chat with their followers/following in the Home screen.

### 2. Screen Archetypes

* Login 
  * User logs in.
* Register
   * User can create an account.
* Stream
   * User can view a feed of likes/comments/posts related to anime shows.
   * User can like/comment.
* Creation 
   * User can create a new post on the Home feed.
* Search
   * User can search for a particular anime based on name in Search tab.   

### 3. Navigation

**Tab Navigation** (Tab to Screen)

* Home feed.
* Discovery feed.
* Profile page.

**Flow Navigation** (Screen to Screen)

* Login Screen
   * Home
* Registration Screen
   * Home
* Stream Screen
   * None, but future versions plan to allow users to click on comment threads under a post and see it in it's own screen.
* Creation Screen
   * Home after making a post to the feed.
* Search Screen
   * Collection view of shows according to queried letters that were input.   

## Digital Wireframes
<img src="https://i.imgur.com/DFyUhic.jpeg" width=600>

## Schema 
### Models
#### Post

   | Property       | Type     | Description |
   | -------------  | -------- | ------------|
   | objectId       | String   | unique id for user posts |
   | author         | Pointer to User| image author |
   | animeId        | String   | unique id for anime referenced in post|
   | post           | String   | post caption by author |
   | postlikesCount | Number   | number of likes for the post |
   | animeLikesCount| Number   | number of likes for that anime |
   | watchlistCount | Number   | number of users that added that anime to their watchlist|
   
### Networking
#### List of network requests by screen
    - Sign In Screen
        - (Read/GET) Query with username and password
    - Sign Up Screen
        - (Create/POST) Create a new user
    - Home Feed Screen
        - (Read/GET) Query all posts where user is author or where author is on user's following list
        - (Create/POST) Create a new like on a post
        - (Delete) Delete existing like
        - (Create/POST) Create a new comment on a post
        - (Delete) Delete existing comment
        - (Delete) Delete post if author is user
    - Create Post Screen
        - (Create/POST) Create a new post object
    - Profile Screen
        - (Read/GET) Query logged in user object
        - (Update/PUT) Update user profile image
        - (Read/GET) Query all posts made by user
        - (Read/GET) Query all animes liked by user
        - (Read/GET) Query all animes watchlisted by user
