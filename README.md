# FriendFinder
Friend Finder - Node and Express Servers : Wk#13

1. Survey has 10 questions. Each answer is on a scale of 1 to 5 based on how much the user agrees or disagrees with a question.

2. `server.js` file has basic npm packages `express`, `path`, `body-parser`

3. `htmlRoutes.js` file include two routes:

   * A GET Route to `/survey` which should display the survey page.
   * A default, `home.html` which displays the home page.

4. `apiRoutes.js` file has two routes:

   * A GET route with the url `/api/friends`. This is used to display a JSON of all possible friends.
   * A POST routes `/api/friends`. This is used to handle incoming survey results and to handle the compatibility logic.

5. Data is stored inside of `app/data/friends.js` as an array of objects in the format below.

{
  "name":"Ahmed",
  "photo":"https://media.licdn.com/mpr/mpr/shrinknp_400_400/p/6/005/064/1bd/3435aa3.jpg",
  "scores":[
      5,
      1,
      4,
      4,
      5,
      1,
      2,
      5,
      4,
      1
    ]
}
```

6. Determining the user's most compatible friend using the following as a guide:

   * Converting each user's results into a simple array of numbers (ex: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`).
   * With that done, comparing the difference between current user's scores against those from other users, question by question. Adding up the differences to calculate the `totalDifference`.
     * Example:
       * User 1: `[5, 1, 4, 4, 5, 1, 2, 5, 4, 1]`
       * User 2: `[3, 2, 6, 4, 5, 1, 2, 5, 4, 1]`
       * Total Difference: **2 + 1 + 2 =** **_5_**
   * using the absolute value of the differences.
   * The closest match will be the user with the least amount of difference.

7. displaying the result as a modal pop-up.
   * The modal display both the name and picture of the closest match.
