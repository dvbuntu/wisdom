---
layout: post
title: Bardic Lore Kids Stories
cover: none.png
date: 2017-04-13 18:15:59 
categories: posts, stream, python, keras, bardiclore
---

While last time I setup the code to enact my epic transfer learning plan, this week was about actually putting some data in.  Thankfully, I was able to find a [Dr. Seuss corpus](https://raw.githubusercontent.com/robertsdionne/rwet/master/hw2/drseuss.txt) as well as a set of [Aesop's Fables](http://www.over-yonder.net/~gollingj/oldpage/text/aesop.txt).  I thought it would make sense to train on Dr Seuss first, being nominally simpler language, and then transfer up to more complex models.

<iframe width="560" height="315" src="https://www.youtube.com/embed/pP7k-1PqH64" frameborder="0"> </iframe>

During the stream, there's not enough time to train these models to completion.  But offline, I let the biggest model train overnight on Dr Seuss.  The result?  Well, it was something:

> oh theer called a call.
> there they call all we likes.
> i hall now house do not hall.
> what a lot og they is nod, and the good! they should then a shall.
> i was for they are dear.
> and then this well feet of a fish.
> i like thing ase ase things and sis.
> you call tat a say. not is a good!
> and the good gust a lido!
> and then he this one hood.
> herd! i have a down.
> and when we said,
> oh u pat he to os of the, he head come old.
> i have no shad was to then moush box of therr will sing.
> whele theyee nerettleeee tleetle bedttle butp as a they...
> homle ha heold.
> then he say!
> i wish not his,
> and she call a pat feat the there.
> here. then thing house like.
> whele, thele things whes to!
> hees they thisgs they gave howtele seeetletle beetles.
> but, what theve lae fleas.
> whis is she theid head a shoull.
> thenee stord a chat the good fish, 
> said thing sand and would bat bere

