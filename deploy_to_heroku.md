# Deploying To Heroku

If you have already deployed your app to Heroku, go on to [Deploying to Heroku again].

## Step 1: Create a Heroku application
Type this in the bash tab (aka terminal):
```bash
heroku create
```
`heroku create` registers a new application on Heroku's system. You should see some output including your new app's URL.

## Step 2: Edit the Gemfile

---

Each application has its own `Gemfile`. Be sure you're opening the one inside your app's folder.

---

Heroku will run our application slightly differently than our development computer does, which requires us to make a small change to our `Gemfile`.

Open the file called `Gemfile` in Sublime Text, or your preferred editor, and find the line containing:

```ruby
gem 'sqlite3'
```

__Remove that line__ and replace it with:

```ruby
group :development, :test do
  gem 'sqlite3'
end

group :production do
  gem 'pg'
  gem 'rails_12factor'
end
```

## Step 3: Apply the Gemfile changes
Type this in the terminal:

```bash
bundle install --without production
```

Every time the `Gemfile` changes, you need to run `bundle install` for the changes to be processed. The processed version of the changes is stored in another file called Gemfile.lock.

## Step 4: Commit the Gemfile changes
There are now changes to `Gemfile` and `Gemfile.lock` that need to be committed before we can push to Heroku.

Type this in the terminal:

```bash
git add Gemfile
git add Gemfile.lock
git commit -m "Changed Gemfile for Heroku"
```

## Step 5: Commit any (other) pending changes to git
Heroku will only receive the files we've committed into our local git repository. So we need to make sure all changed files have been committed.

Type this in the terminal:
```bash
git status
```
`git status` shows you any pending changes you've created. If it has no output, you're already ready to deploy! Otherwise...

Type this in the terminal:
```bash
git add .
git commit -m "Some helpful message for your future self"
```
Your commit message should reference whatever your outstanding changes are: something like "Added votes to the topics index".

## Step 6: Push changes to Heroku
Type this in the terminal:
```bash
git push heroku master
```
This takes all changes you've committed locally and pushes them to Heroku.

## Step 7: Run database migrations on Heroku
Type this in the terminal:
```bash
heroku run rake db:migrate
```
This tells Heroku to run your migrations on its database, like running rake db:migrate locally.

Heroku's database is separate from the one on your computer (or the one in cloud9), which means it needs to be updated every time you make changes to the structure of your database.

It also means that you'll not see any of the data you entered into the sqlite3 database on your computer.

## Step 8: Visit your application
Type this in the terminal:
```
heroku apps:info
```

This will display a listing of information about your Heroku application.  One useful bit of information is your application's `Web URL`.  You can copy this URL, open up a new browser tab and paste it into the address bar to see your application running on Heroku.

## Explanation
First, we had to do some work to make Heroku happy with our application. This required updating the `Gemfile` and bundling.

* The `Gemfile` is a list of all the Ruby libraries your application needs. What we've declared here is that we want to use the `sqlite3` library while we're developing on our computer (the development group) but when deploying to Heroku (the production group) we want to use the pg library, which is made for the type of database that Heroku uses.

* Bundler is how Ruby projects keep track of the gems that they use. We told Bundler what we wanted to use in the `Gemfile`, now we need to make sure those gems are installed. Since we don't have the type of database Heroku does, we skip the production gems. Don't worry though! Bundler still logs them so Heroku will install them when they get your code.

You should be able to deploy your application any time it's in a good, working state. Your typical workflow will look like:

  1. Add or change some code
  1. Test your changes locally (or on cloud9)
  1. Commit your changes (git commit)
  1. Deploy changes to Heroku (optional)
  1. (repeat)

Any time your changes are committed, you should feel free to `git push heroku master` and boom! Your changes are live!
