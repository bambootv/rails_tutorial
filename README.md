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
