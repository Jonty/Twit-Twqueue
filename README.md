Twit-Twqueue
============

Twit-Twqueue is a terribly named tool that allows multiple people to post to a
twitter account by sending it direct messages. The tweets can be queued up and
posted periodically or posted immediately. It was written for use at
@londonhackspace and @bashtips.

Installation
------------

Requires Python and some form of cron-type daemon. All dependencies are bundled.

Usage
-----

* Run ./twit-twqueue in a terminal and it'll give you a twitter URL to visit,
  then prompt you for the authorisation code you are given after logging in.
  
* In case it's not blindingly obvious, the account you log in with is the
  account that will be posted to.

* Add `twit-twqueue -fp 100` to cron, executing however often you would like
  tweets to be posted. This will fetch all new DMs and queue them (-f) and post
  100 messages from the queue (-p 100).
  
* If you want tweets to be queued up and only have one posted at a time, just
  pass -p 1 instead of -p 100. You can run `./twit-twqueue -f` more often to
  populate the queue if you wish.

* Only people the account is following can DM it, so you'll have to follow the 
  people you want to post to the account.

* Queued DMs are stored in tweets.txt in the local directory, one-per-line. You
  can edit this file at will.

* More help is available with ./twit-twqueue --help
