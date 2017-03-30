---
layout: post
title: Bardic Lore Basic Model
cover: none.png
date: 2017-03-30 17:00:09 
categories: posts, stream, python, keras, bardiclore
---

After the [Keras 2 Launch Video](https://youtu.be/9VFIZ3aaFPY), it's time to get back new models, which means more regenerating Shakespeare.  [Last time](https://youtu.be/xQlhFj2NcEM), we stripped down all the Bard's works to a small set of characters and setup a basic LSTM model.  But after training, it spit out mainly white space. Not very impressive.  Since then, I realized that I significant number of lines in the text are leading whitespace with a single digit (as for the sonnet numbers).  These will no doubt pollute the model, especially if the number of white spaces was greater than the unroll length.  Removing extraneous spaces, the model improves.

<iframe width="560" height="315" src="https://www.youtube.com/embed/pP7k-1PqH64" frameborder="0"> </iframe>

Training the model briefly during the stream, we saw it at least learn how long words are.  Offline, I let it learn overnight, reaching about 50% validation accuracy.  Nothing too amazing, but let's take a look at some generated text:

```
r els entreat me to learn me hath the death to make with a man to can the head;
 englon came our duke of gentle wood of my house with thy sends of lading and dumpers of the stanf
 than so much that the world of hot stand a prince;
 but i am to do stand, and i have the enemy of the life and thou doth but you do the stand of the fortunes of soul to conferer.
 my lord, and the garter are or to the pardon of the graces as so, and he would not the man, when they are good nor and your or others
personal use only, and are but the while of my gracious bottom of the true man,
 i will you shall for the son of the horses.
 but i shall see him be a fair duke of the which i should to arm'd it of the deadful honest of the are 
 may i will did the stans bowes a sort 
 the rage as the prince, that i will see the capalous lords.
 but in the stand the complete bear a world with like the sent of the morting sail. 
 who should come to my lords of the prince to deserve the stay of the lady 
 but the more heart
```

Depending on your opinion of Middle English, you might say this is just as intelligible as the source text :p
