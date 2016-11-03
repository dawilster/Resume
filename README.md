**William Porter**
==============
To get to know me as a dev it would probably help to here about my typical stack. I specialise in building apps built in Rails and Ember.js. I've built in APIs to back Ember.js, iOS and Android application. And I've built funky and fluid single page apps in Ember. 
We deployed all our apps to AWS **EC2**, backed it with **PostgreSQL** RDS and cache it with **Redis** ElastiCache.

Other than that I've been in the tech space for almost 5 years now, I'm an avid traveller (I'm currently calling Toronto home) and learn through the people around me and my experiences. 

LINKS
----------
You can find some code I've committed here https://github.com/dawilster and my not so up to date LinkedIn here https://www.linkedin.com/in/william-porter-779b7039.  

EXPERIENCE
----------

2016 (4 months) -  [Pick PETE](http://pickpete.com)

> **Senior Full Stack Developer**

Imagine fantasy league but for reality television. Built on a Rails/Ember stack I had the opportunity to deep dive into both frameworks and oversee a small team. In a small amount of time we were able to build out a killer new feature at the same time optimising and scaling the existing codebase and infrastructure.

2013 - 2016 - [Papercloud](https://www.papercloud.com.au)

> **Software Developer**

Ruby/Javascript developer. Working for an agency I got to work on a variety of small to large scale projects. Developed primarily backend API’s as well as front end web applications. But had a lot of exposure to a variety of software ranging from Ember.js to iOS.

2010 - 2012 - [PSDtoBootstrap](https://www.psdtobootstrap.com)

> **Lead Developer**

Had the opportunity to work for myself building a large amount of quality HTML templates. I built templates with Twitter Bootstrap as the foundation. This period of my life was amazing with developing my frontend skills and the education was priceless. 

SOME PAST WORK
----------
[**NBC MatchMaker**](https://itunes.apple.com/us/app/nbc-sports-matchmaker/id952349002?mt=8): Built and optimized a backend stack that supports both our iOS and Android apps which at it's peak was supporting over 30,000 users. Was built with scale in mind, endpoints were properly speed and load tested. And utilized Redis as our memcache to improve load times. 

[**My Healthy Travel**](myhealthytravel.com.au): Had the amazing opportunity to spearhead development on a web application in Ember.js. The framework is great example of frontend development done right, the testing framework and the ease that you could mock API endpoints increased productivity immensely.

THINGS OF NOTE
----------
I breath **Test Driven Development**. All my Ruby development begins with test cases.  
Some testing tools I couldn't live without **RSpec, FactoryGirl and VCR** 

[Source File - service.rb](https://github.com/Papercloud/social_auth/blob/master/spec/models/service_spec.rb)

```ruby
describe "self.create_with_request" do
  def valid_service_from_request
    Service.create_with_request("1", @user, "Authenticated",{access_token: "access_token"})
  end

  it "creates an Authenticated method service if remote id doesn't exist" do
    expect{
      valid_service_from_request
    }.to change(Service, :count).by(1)
  end

  it "Can create a connected service even if an authenticated service belonging to another user already exists" do
    service = Service.create(access_token: {access_token: "access_token"}, remote_id: "1", user: User.create, method: "Authenticated")
    expect{
      Service.create_with_request("1", @user, "Connected", {access_token: "access_token"})
    }.to change(Service, :count).by(1)
  end

  it "creates service with type set to authenticated" do
    expect(valid_service_from_request.method).to eq "Authenticated"
  end
end
```

**Commit messages are the best!**
They're are best tool in communicating to future developers and even ourselves why we did what we did. 
Plus it makes reviewing Pull Requests a dream!

```
commit 24fe6f54646af6dc9cdea7beffe90ce712c36c74

  Move pickCollection out of afterModel()

  Not necessary since no promises are returned. Initial reasoning was that the pickCollection was persisted before the controller was loaded but works fine with only pushing the pickCollection to the backend once picks have been created.

commit 5dd58061ea58cb247c7bdae91a2901380e7de4dc

  Not necessary since no promises are returned. 

  Initial reasoning was that the pickCollection was persisted before the controller was loaded but works fine with only pushing the pickCollection to the backend once picks have been created.

commit 5dd58061ea58cb247c7bdae91a2901380e7de4dc

  Fix comparison order error

  Was calling interactWithEvent before checking subEvent was nil. So essentially passing a null event all the time

commit 737956f1d9cc714c2a74f608db1656719cf6d7f1

  Override save() instead of implementing an additional commit() method

  This way future saves won't have to apply the new commit() method
```

CODE I'M PROUD OF
----------
**social_auth** - [Github Repo](https://github.com/Papercloud/social_auth)
 Login with FB/Twitter/G+ was such a recurring feature over all our iOS/Android but we didn’t have a common standard to use across all our API. Each time we were essentially rewriting both Rails and iOS to do the samething.

**notify_user** - [Github Repo](https://github.com/Papercloud/notify_user)
The backbone of all our backend applications at Papercloud. It’s responsible for managing/sending notifications (web/apns/gcm) to all our users. In use in applications with over 200,000 users. Also handles all our notification aggregation. 

EDUCATION
----------
**Bachelor of Computer** - ( 2012 - 2016 )

*RMIT (Melbourne, Australia)*

A FEW SKILLS I KNOW 
----------

 - Ruby/Ruby on Rails
 - Javascript 
 - Test Driven Development (TDD) 
 - HTML/CSS 
 - PostgreSQL 
 - Objective-C 
 - Git 
 - AWS, RDS, EC2 
 - Redis  
 - Sidekiq
