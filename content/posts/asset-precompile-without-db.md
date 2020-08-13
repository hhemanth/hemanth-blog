---
title: Asset Precompile without accessing the database
description: "How to precompile assets when you dont have access to the database"
date: 2020-08-13
lastmod: 2020-08-13
tags: [rails, assets, precompilation, flat_map, detect, arrays]

---

I am currently working on a large rails project, infact its a huge project. The problem we were having is that the ec2 instances would take more than 10 mins to warm up before they would start accepting traffic. The reason why they would take so much time to warm up is they are precompiling assets. 

Now you would ask, why can't you precompile them and store when creating the AMI in the first place. The answer is the machine building the AMI doesnot have access to the database. So we couldn't precompile the assets, as usually while precompiline, you would need DB access.

But we needed to reduce the time it took for the instances to warm up, so I went looking to find ways to precompile assets without accessing the DB. I did fine a way. 

```ruby
# Gemfile
gem 'activerecord-nulldb-adapter'
```
Then run bundle install 

```yaml
#databse.yml
production:
  adapter: <%= ENV['DB_ADAPTER'] ||= 'postgresql' %>
```

Then run 
```shell 
> DB_ADAPTER=nulldb RAILS_ENV=production rake assets:precompile
```

Then you will be able to precompile the assets without needing access to the DB. One more thing you have to take care is the initializers. you may have some code in your initializers which may be accessing the database. you need to wrap it in a conditional

```ruby
#initializers/acces_db.rb
if  ENV['DB_ADAPTER'].blank?
    #code accessing DB
    ...
    ... 
end

```