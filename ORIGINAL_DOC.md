## PodGrab – A Command Line RSS Podcast Downloader Written In Python

Posted on December 31, 2010 in Code, Linux, Open Source

http://joshua14.homelinux.org/blog/?p=492

I’ve been using gPodder as a podcast downloader for quite a while, which is great for a desktop system like Ubuntu, but less awesome (i.e. can’t be done) for cron-jobbing on my server. What I wanted was something I could use to store my podcast subscriptions and set it up as a cron job on my server and download all my podcasts to my server whenever there was a new episode out. I had a look around on the net for an RSS-based podcast downloader for the command line and couldn’t find one. I mean, not one.
Since I’ve been meaning to learn Python for quite a while, I thought this would be the ideal opportunity to learn a bit of Python and get a useful tool out of it that I could actually use. So, without further ado, I present to you PodGrab, my Python podcast downloader.

It is very simple to use although if you’re using Windows, you may need to download some extra modules – but since this isn’t a Windows site we’ll forget about that :)

Once you’ve downloaded it, you can add a new feed URL with: –

```PodGrab.py -s http://some.feed.url.xml```

This will store the feed as a subscription and download the latest episode. Sometimes (as I have wanted to do in the past), you simply want to download all episodes of a particular podcast without subscribing to it. You can do this with: -d

```PodGrab.py -d http://some.feed.url.xml```

If you want to list your current subscriptions, you can use: -l

```PodGrab.py -l```

which will list all your current subscriptions. You can delete a subscription with: -un

```PodGrab.py -un http://some.feed.url.xml```

The program also has the ability to mail you if you add an e-mail address, list mail addresses and such. Type

```PodGrab.py -h```

for a full list of command line switches. To update your podcast subscriptions when using in conjunction with cron, you simply use: –

```PodGrab.py -u```

and the program will check each feed for a new episode. By default, all podcast downloads are stored in a subdirectory called “Podcasts” off wherever you run PodGrab for the first time, but this is easily changed in the code if you desire. The subscriptions are all stored in a file called “PodGrab.db” which is a small SQLite database. In a future version, I may add MySQL support.

Anyway, you can download PodGrab here. I hope it’s useful to somebody. If you find any major bugs or suggestions for improvements, my e-mail address is in the code. I hope you enjoy it :-)
