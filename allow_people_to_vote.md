# Allow People To Vote

## Goals
Now we're going to add a button people can click to cast a vote.

## Steps
### Step 1: Add a new controller action for voting
Edit `app/controllers/topics_controller.rb` and add this method at the end of the controller, above the `private` keyword:

```ruby
def upvote
  @topic = Topic.find(params[:id])
  @topic.votes.create
  redirect_to(topics_path)
end
```

* `@topic = Topic.find(params[:id])` finds the topic in the database with that id and stores it in the variable @topic.
* `@topic.votes.create` creates a new vote for the current topic and saves it in the database.
* `redirect_to(topics_path)` tells the browser to go back to `topics_path` (the topics list).

### Step 2: Add a new route for voting
Open `config/routes.rb` and find the section that looks like this:

```ruby
resources :topics
```

Replace that line so it looks like this:

```ruby
resources :topics do
  member do
    post 'upvote'
  end
end
```

Verify that upvote route was added successfully by checking the output of `rake routes`. You should see a line that looks like this:

```bash
      Prefix Verb   URI Pattern                  Controller#Action
upvote_topic POST   /topics/:id/upvote(.:format) topics#upvote
```
### Step 3: Add the button to the view
Edit app/views/topics/index.html.erb so that the bottom loop looks like this:

```ruby
<% @topics.each do |topic| %>
  <tr>
    <td><%= topic.title %></td>
    <td><%= topic.description %></td>
    <td><%= pluralize(topic.votes.count, "vote") %></td>
    <td><%= button_to '+1', upvote_topic_path(topic), method: :post %></td>
    <td><%= link_to 'Show', topic %></td>
    <td><%= link_to 'Edit', edit_topic_path(topic) %></td>
    <td><%= link_to 'Destroy', topic, method: :delete, data: { confirm: 'Are you sure?' } %></td>
  </tr>
<% end %>
```

* `pluralize(topic.votes.count, "vote")` displays the number of votes the topic has, plus the word "vote" or "votes" accordingly.
* `button_to '+1'` creates an HTML button with the text "+1".
* `upvote_topic_path(topic)` creates the appropriate URL for the action we want to invoke. In this case, we want to upvote the current topic.
  * `upvote_topic_path(topic)` would return `/topics/42/upvote` (if topic.id was 42)
* `method: :post` ensures we do the create action of CRUD, not the read action.

### Step 4: Confirm your changes in the browser
Go back to and refresh the app in the other web browser and try out the latest changes.

Revel in the fact that you didn't have to restart the server to see these changes. Hawt, no?

Next Step:
Go on to [Redirect To The Topics List After Creating A New Topic](redirect_to_the_topics_list_after_creating_a_new_topic.md)
