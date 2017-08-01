# Sample_app

## Chapter 1:

#### Doc
[Learn enough to be dangerous](https://www.learnenough.com)

#### MVC
![](https://user-images.githubusercontent.com/18675907/28787437-69bda5f6-7646-11e7-9094-f3ab10af2efd.png)

#### Git config
```
git config --global user.name "HoanKi"
git config --global user.email "hoanki2212@gmail.com"
```

```
New ssh key
  ssh-keygen -t rsa -C "hoanki2212@gmail.com"

Find ssh key at: ~/.ssh/id_rsa.pub
  ssh-rsa AAxxxBBBB
  hoanki2212@gmail.com

```

#### Deploy to heroku

```
Use gem pg to deploy database in heroku host.

  group :development, :test do
    gem 'sqlite3', '1.3.13'
  end

  group :production do
    gem 'pg', '0.20.0'
  end
```

```
bundle install --without production
```

[How to deploy to heroku](https://devcenter.heroku.com/articles/heroku-cli)

Some command:
```
Install:  wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh | sh
Version:  heroku version
Login:    heroku login
SSH key:  heroku keys:add
New app:  heroku create
Rename:   heroku rename new_name
Push:     git push heroku master #(master of local to master of heroku)
          git push heroku develop:master #(develop of local to master of heroku)
```

## Chapter 2:

#### Url
```
HTTP Request  Url           Action          Purpose

GET           /users        index           show all users
POST          /users        create          new users
GET           /users/1      show            show uses with id 1
GET           /users/new    new             make new user
GET           /users/1/edit edit            edit user with id 1
PATCH         /users/1      update          update user with id 1
DELETE        /users/1      detele          delete users with id 1
```

#### MVC

![](https://user-images.githubusercontent.com/18675907/28814626-5843e5a8-766c-11e7-81be-49895750bfa5.png)

#### Association
```
$ rails console
>> first_user = User.first
=> #<User id: 1, name: "Michael Hartl", email: "michael@example.org",
created_at: "2016-05-15 02:01:31", updated_at: "2016-05-15 02:01:31">
>> first_user.microposts
=> [#<Micropost id: 1, content: "First micropost!", user_id: 1, created_at:
"2016-05-15 02:37:37", updated_at: "2016-05-15 02:37:37">, #<Micropost id: 2,
content: "Second micropost", user_id: 1, created_at: "2016-05-15 02:38:54",
updated_at: "2016-05-15 02:38:54">]
>> micropost = first_user.microposts.first    # Micropost.first would also work.
=> #<Micropost id: 1, content: "First micropost!", user_id: 1, created_at:
"2016-05-15 02:37:37", updated_at: "2016-05-15 02:37:37">
>> micropost.user
=> #<User id: 1, name: "Michael Hartl", email: "michael@example.org",
created_at: "2016-05-15 02:01:31", updated_at: "2016-05-15 02:01:31">
>> exit
```
