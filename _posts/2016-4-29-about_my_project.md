---
layout: post
title: I may have found your credentials
---

If you found this page, you probably got an email from me. Here's what I'm doing. I'm currently developing a project that looks for people's credentials posted to github. When I find those credentials, I send the person who made the commit an email, letting them know that their credentials have been compromised. Here are some common questions I get:


Do I really need to change my AWS secrets? Deleting my repository isn't enough? 

Yes and Yes. As soon as you make your code public, any sensitive data is already compromised. I found your code within 1 or 2 minutes of you publishing it and I am sure I'm not unique. The only way to be safe is to change your credentials. In fact, if you change your credentials, you don't really need to delete your repository. You will just have some useless credentials in a previous commit. Which might be embarassing, but that's all. 


But the credentials were only for a S3 database, and there was no sensitive data in there. Is that a problem?

It still might be a problem. The problem is that if your credentials are root account credentials (and I don't know if they are or not), then they can be used for all of the aws services. People can actually use those credentials to spin up a bunch of servers and mine bitcoins (or do what ever they want to do with those credentials). That could end up costing you a bunch of money.


How do you do this?

Right now I don't really feel comfortable sharing that information, as I do not want to help people who might want to find and use api keys. Suffice it to say that github has an api (https://api.github.com/events) which continuously delivers the most recent public activity on github. I scan through these recent events looking for things that appear to be sensitive information. I'm not 100% accurate. I miss some credentials, and get a few false positives. But I do the best I can to be helpful, while not spamming everyone


Are you associated with github?

Nope, I'm just someone trying to help out.


I'm always happy to hear feedback or answer questions. My email (in case you came to this page without getting an email from me) is helpfulowl500@gmail.com
