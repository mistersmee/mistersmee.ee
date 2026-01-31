+++
title = "Self-hosted Services, oh my!" +++


I've had a blast these past few days figuring what I can and can't self-host, what I should and should not self-host. I've taken inspiration from Luke Smith - though I disagree with a lot of his views ___heavily___, I can't deny his [https://landchad.net](https://landchad.net) wasn't a big influence, even though it's kinda unmaintained and very out of date on some of the topics. The man had a huge influence on my early Linux journey, though I've long since moved on from it.


Wolfgang from Wolfgang's Channel, I've taken more of an inspiration from, *clearly*, since the design that this very website is using is pretty much kanged from his website: [https://notthebe.ee](https://notthebe.ee). Hell, I found out I could have a website with the `.ee` extension from him, which suits me nicely with my nick. So much of my Linux early knowledge and introduction was from Luke Smith, Brodie Robertson and the rest, but Wolfgang had the most impact, I guess, including my love for Nord.


## Current self-hosted services live on this domain/VPS:

- [Microbin](https://microbin.mistersmee.ee), a pastebin.
- [SearxNG](https://searx.mistersmee.ee), a metasearch engine.
- A WireGuard tunnel, effectively making it a self-hosted private VPN I can use.
- A Matrix homeserver, using Conduit, at `matrix.mistersmee.ee`. It's single-user, only for me, so don't try to join, please.
- A coturn server, for Matrix and other services, probably.


## My considerations when choosing what to host


The main consideration is the fact that this is hosted on a VPS. Hence, it doesn't have a lot of storage.


So, most of the services that ideally you'd like to host with a lot of storage, like your Immichs, Nextclouds and Forgejos are automatically out, because photos and large documents usually take up a lot of space, if you have a lot of them like I do, and even though most git repos are a few megabytes, some repos do get large.


Not to mention Jellyfin and the -arr stack and whatever that's even tangentially related to those is also out due to the same reason.



Finally, another major consideration is that I’m primarily hosting these services for my own use, not for a group. Because of that, it doesn’t make much sense to run software that’s fundamentally designed for communities, like Pleroma, Mastodon, Matrix or XMPP servers, Mumble, and stuff like that.



The main exceptions would be an ActivityPub service, most likely Lemmy or Mastodon, since I’d like to self-host one to retain full control over my data and have administrative control over the instance. Ideally, it would be a single-user instance, so I can follow whoever I want without having to think about other users on the server. Matrix is another possible exception for similar reasons, although I haven’t fully worked through the Matrix documentation yet.



Unfortunately, Lemmy is off the table for now for two reasons: first, I can’t get it to compile from source on my VPS because the Rust build keeps failing due to the RAM being insufficient or something, and second, the documentation is in pretty rough shape. From what I can tell, the project was moved between repositories, and parts of the documentation still reference the old one, so there are gaps and broken assumptions throughout.



Mastodon is also out as it has an email server as one of its dependencies, and a self-hosted email server is a no-go. Hetzner blocks port 25 by default, and while you can submit a request to have it unblocked, it doesn’t seem as straightforward as it used to be. The wording on their support article isn’t especially encouraging about the likelihood of the request succeeding, they manually review on a case-by-case and need-by-need basis apparently. It’s a bummer, because I really wanted to host my own email server, but it is what it is. I can use an external email service and use port 587 and that would probably get Mastodon working, but that kinda defeats the purpose of self-hosting stuff, so I don't like that option.



XMPP is still pretty much a non-starter as well. It’s even less widely used than Matrix, and these kinds of platforms only make sense if you actually have people to talk to. Everyone I know is on WhatsApp and isn’t going to switch, so hosting XMPP just doesn’t make much sense for me. There are at least communities that have formed on matrix.org that I can join, I don't think XMPP has that.


Jitsi falls into a similar category. It’s designed for hosting web meetings with multiple people, and that’s not something I really do. I suppose I could use it as a replacement for the occasional Google Meet, but there’s another issue: Jitsi still hasn’t properly caught up with Debian 13. Their package depends on OpenJDK 17 or 11, both of which were removed in Trixie, so the package is currently broken.



## Future stuff to self-host



Let's see what comes up next in my spree to self-host everything. Hopefully I can get through the Lemmy documentation again, so I can decide finally whether to do it or not, and figure out the best way to do Matrix by going through its documentation finally and decide on that too. I'll probably go through my docments and photos library, and my git repos, to re-evaluate my decision too.


And hopefully the Jitsi people finally get around to fixing their package.



As for the rest of the self-hosting world, I'll keep looking for something that's cool to self-host and fits in the considerations and then experiment with it.


Adieu for now!


UPDATE 2026-01-31: Unfortunately, Lemmy is out because of similar reasons to Mastodon, it also requires an email server, so no cigar. Onwards to Matrix and their documentation.

UPDATE 2026-01-31 2: Matrix is up! Ping me at `@mistersmee:mistersmee.ee`. It's a single-user homeserver, so don't try to join it, please. I'll look at the sizes of my git repos, photos and documents and re-evaluate my decision to not host Immich, Forgejo and Nextcloud, next.
