---
layout: post
title: I may have found your credentials
---

If you found this page, you probably got an email from me. Here’s what I’m doing. I’m currently developing a project that looks for people’s credentials posted to github. When I find those credentials, I send the person who made the commit an email, letting them know that their credentials have been compromised. Right now I am focusing on aws credentials, as these seem to be the most often abused. To read a decent write-up of how to handle aws credentials and what to do if they are compromized, go here: http://zacharybears.com/amazon-aws-account-hacking-and-how-to-avoid-it/

Here are some common questions I get:

**now that I've posted my secrets on github, what do I do?**

1. You should first change your aws credentials. As soon as you push code to Github, you should treat any exposed credentials as compromised. This page describes how to delete and reset aws credentials: http://docs.aws.amazon.com/general/latest/gr/managing-aws-access-keys.html
2. Second. Look at your account to see if anyone has already started to use it. Go through all the AWS services to make sure no one messed with anything else. (in particular look for ec2 instances in all the regions). An easy way to know where to look is to go to your billing page and view all the areas that accumulated charges for the month.
3. If you see any suspicious activity, contact aws support.
4. Then you should use a safe method to manage your credentials in your code (i.e. by using env variables or a config file that is ignored through .gitignore)

**Do I really need to change my AWS secrets? Deleting my repository isn’t enough?**

Yes and Yes. As soon as you make your code public, any sensitive data is already compromised. I found your code within 1 or 2 minutes of you publishing it and I am sure I’m not unique. The only way to be safe is to change your credentials.
But the credentials were only for a S3 database, and there was no sensitive data in there. Is that a problem?
It still might be a problem. The problem is that if your credentials are root account credentials (and I don’t know if they are or not), then they can be used for all of the aws services. People can actually use those credentials to spin up a bunch of servers and mine bitcoins (or do whatever they want to do with those credentials). That could end up costing you a bunch of money.

**How do you do this?**

Right now I don’t really feel comfortable sharing that information, as I do not want to help people who might want to find and use api keys. Suffice it to say that I have built a web scraper that looks for things on github that appear to be credentials. I’m not 100% accurate. I miss some credentials, and get a few false positives. But I do the best I can to be helpful, while not spamming everyone

**Are you associated with github?**

Nope, I’m just someone trying to help out.

I’m always happy to hear feedback or answer questions. My email (in case you came to this page without getting an email from me) is helpfulowl500@gmail.com

