# Redirect To The Topics List After Creating A New Topic

## Goals
When a user creates a new topic, or edits an existing topic, they are currently shown a page with just that topic. For our voting app it makes more sense that they would be taken back to the topic list.

In this step we'll change the flow of our app so that the user is taken back to the topics list after they add a new topic (create) or edit an existing topic (update).

## Steps
### Step 1: Change the topics controller
Open `app/controllers/topics_controller.rb` and look at the create method.

Find the line:

```ruby
format.html { redirect_to @topic, notice: 'Topic was successfully created.' }
```

and change `@topic` to `topics_path` like this:

```ruby
format.html { redirect_to topics_path, notice: 'Topic was successfully created.' }
```

so that the file looks like this:

```ruby
def create
  @topic = Topic.new(topic_params)

  respond_to do |format|
    if @topic.save
      format.html { redirect_to topics_path, notice: 'Topic was successfully created.' }
      format.json { render :show, status: :created, location: @topic }
    else
      format.html { render :new }
      format.json { render json: @topic.errors, status: :unprocessable_entity }
    end
  end
end
```

In the same file, locate the update method.

Find the line:

```ruby
format.html { redirect_to @topic, notice: 'Topic was successfully updated.' }
```

and change `@topic` to `topics_path` like before:

```ruby
format.html { redirect_to topics_path, notice: 'Topic was successfully updated.' }
```

### Step 2: Confirm your changes

Go back and view your application (press `Run Application` if necessary).  If running locally you can go to `http://localhost:3000`

## Explanation
`format.html { redirect_to topics_path, notice: 'Topic was successfully created.' }`
* format.html means that the server should send HTML back to the browser
* redirect_to topics_path means show the topics list page when we're done creating or updating a topic
* notice: 'Topic was successfully created/updated.' puts the message into the flash so it will be displayed on the topics list

## Next Step:
Go on to [Make The Topic Title A Link](make_the_topic_title_a_link.md)
