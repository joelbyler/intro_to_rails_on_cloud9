# Creating A Migration

## Goals

  |Topics     |
  |-----------|
  |id         |
  |title      |
  |description|

The suggestotron has a list of topics that people can vote on. We'll store our topics in the database. In this step you'll do the following:

* Create a simple Table in the database for topics with a title and a description

* Automatically generate the corresponding Scaffold in Rails (namely, the Model, the View, and the Controller).

## Steps
### Step 1
Type this in the terminal:
```bash
rails generate scaffold topic title:string description:text
```
* `generate scaffold` tells Rails to create everything necessary to get up and running with topics.
* `topic` tells Rails the name of the new model.
* `title:string` says that topics have a title, which is a "string".
* `description:text` says that topics have a description which is a "text". (What's the difference between "string" and "text"? Basically "text" is for strings that might be very long.)
If you want, take some time to poke around the files listed in this step. You can learn about them in the Rails Architecture page.

Go on to Rails Architecture

### Step 2
Type this in the terminal:
```bash
rake db:migrate
```
This tells Rails to update the database to include a table for our new model.

## Explanation
__Rake__

`rake` (__r__uby m__ake__) is a tool that allows you to run small Ruby programs (tasks) that you use often in your application.

Here, `rake db:migrate` is a task provided by the Rails framework. It uses the migration file we just created (`db/migrate/201xxxxxxxxxxx_create_topics.rb`) to change the database. Database migration files can be crucial to code collaboration.

---

You can run rake -T to see a list of all the rake commands your app currently responds to, along with a short description of each task.

---

## Next Step:
Go on to CRUD With Scaffolding
