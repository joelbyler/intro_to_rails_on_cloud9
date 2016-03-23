# Credits And Next Steps

Guess what? ***You're done!!!*** Congratulations, you just "finished" your first rails app!

(They're never *really* ever finished... have fun tweaking it!)

You get another sticker! :)

## Extra Credit
If you got all the way through Suggestotron with some time to spare, here's some extra stuff you can try:


* You've been working on the cloud the entire time, but now you can [Deploy your application to Heroku](deploy_to_heroku.md)
* Share your code! Create a [GitHub](https://github.com/) account, add a repository there, and push your git repository to a new `remote` / github.
* Add a downvote button that does the opposite of what the upvote button does
* Create upvote and downvote methods in the Topic model and use those in the topics controller instead directly modifying the topics votes
* Sort topics by their number of votes
* Add an 'about' page, linked from the bottom of the Suggestotron topics list. Link back to the Topics list from the About page so users don't get stranded.
* If your class has a __lot__ of time left over:
  * Users should be allowed to vote only once: give votes a user_id and allow a user to have voted on each topic only once. But wait, what is a 'user' in our system? Get a volunteer to introduce everyone to [Devise](https://github.com/plataformatec/devise), a simple way to add authentication to a Rails application.
  * Users should be able to give a post a 'negative' vote instead of a positive one. How might you represent that in this system?

## Authors
* The [RailsBridge community](https://github.com/railsbridge/docs/graphs/contributors)
* ...and maybe you? Pull requests welcome on [GitHub](https://github.com/railsbridge/docs)

## What next?
* Probably time for the closing presentation.
* After that, start a project, tutorial, and come back again!
* All our favorite resources can be found on the RailsBridge site: [http://railsbridge.org/learn/resources](http://railsbridge.org/learn/resources)
* Also you can get a deeper look into the world of Ruby on Rails by reading the [Rails Tutorial book online](https://www.railstutorial.org/book/) which includes special guidance for folks who are using the cloud9 IDE to develop their Rails applications
