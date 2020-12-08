---
layout: post
title:      " How to db:seed"
date:       2020-12-08 20:24:13 +0000
permalink:  how_to_db_seed
---


Seeding was and is still new to me although it gets easier over time.  When working on a the backend is becomes cumbersome to to create data.  Depending on your attributes and your relationships it could take a lot of typing and time wasted where you could have been writing more methods.  So I found that 'Faker' helped take care of that issue.

Faker is an open source library with an array of subjects from numbers to sitcoms to dates, the list is almost endless.  

To get started with faker you install in to your backend repo just like a gem.

```
gem install faker
```

Within your db file there is a `seeds.rb` file that is where you will place the faker data.  You an create one entry to hundreds of them depending on your needs are.  Here is an example of how you can get it going:


One entry:
```
 Career.create( position: Faker::Construction.trade, yrs_experience: Faker::Number.within(range: 1..10))
 
#=> "Carpenter" 
#=> 7
```

Or one can have ten entries:

```
10.times do
Career.create( position: Faker::Construction.trade, yrs_experience: Faker::Number.within(range: 1..10))
 
```

The output of the 10 times do will be ten random files.

You are welcome to create your own data or use faker but I'd say faker is the way to go to save you time.

