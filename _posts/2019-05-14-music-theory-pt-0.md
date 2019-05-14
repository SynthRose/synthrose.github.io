---
layout: post
title: 'Music Theory Pt. 0: Frequency Fundamentals'
date: 2019-05-14 00:00 -0700
tags: music-theory music science
---

Given the near-boundless variety of human cultures found throughout the world, there are few things that are true [cultural univerals](https://en.wikipedia.org/wiki/Cultural_universal) &mdash; features found in every culture anthropologists have ever examined. Music is one of them. It is an everpresent part of human life, and in the modern age of YouTube, Spotify, iTunes, and radio stations, it is easier to access than ever. Music has the power to connect us, bring us to tears, keep us motivated to work and study, and inspire us to dance into the night. You might even be listening to some right now.

So it would probably be nice to understand it.

To be clear, I'm nowhere near qualified to talk about music. I'm not an expert on music theory, I can't play an instrument, I can barely sing, and every attempt I've made at composition has been a failure. But I'm going to write some blog posts about it anyway with all the [cocky](https://www.smbc-comics.com/comic/2014-12-30) [overconfidence](https://xkcd.com/793/) of a physics undergrad, because I am one, and because it's a topic that interests me greatly. The focus of this series of posts will be on the science and especially the mathematics of music. If you spot an inaccuracy or a misleading explanation, please let me know so I can fix it! My Twitter and GitHub accounts are linked at the bottom of the page.

### Sound, and the Sensation Thereof

Normally, the first sections of music theory resources are spent introducing the musical staff, clefs, note names, and that sort of thing. But this presupposes a lot - why should we think to arrange notes on a staff? Why should they be labelled with seven letters? After all, there are 12 notes on a piano &mdash; so shouldn't there be 12 letters? And why *are* there 12 notes on a piano? Hell, why do we even arrange music into notes in the first place? Clearly, we should start at first principles here. And for music, that means we need to talk about sound.

A sound is really just a vibration through a medium (which is to say, air, unless you're reading this post underwater or while burning to death in a pool of lava). When an object, such as a string, a membrane, a reed, an air column, or a loudspeaker vibrates, it knocks away the air molecules nearby. Those then knock into the air molecules next to them, and so on, creating a wave of higher density, and thus higher pressure, air. Behind that wave, there is now a void with a lower density of air, and thus a lower pressure. As the object continues to vibrate, this pattern repeats, and you get a sound wave. 

![A longitudinal wave, with particles oscillating from side-to-side in alternating compression and expansion.](/assets/music-theory/longitudinal.gif)
*A longitudinal pressure wave.*

This regular pattern of compression and expansion can be modelled mathematically as a sine wave with a certain amplitude (the "height" of the wave) and period (the "length" of a cycle expressed in units of time). The period can also be expressed as a wavelength (the length in units of space), or, most commonly, as frequency &mdash; the number of cycles per unit time. The most common unit of frequency is the hertz (Hz), equal to one cycle per second.

![Components of a sine wave, expressed as displacement over time. The amplitude and period are labelled.](/assets/music-theory/sine-wave.svg)
*The components of a sine wave.*

When these pressure waves reach the ear, they vibrate the eardrum, which then vibrates a bunch of other crap in our ear, which then in turn vibrate hair cells, which rub against some other stuff that releases chemicals, and those chemicals activate neurons that send a signal to the brain. The details aren't really that important &mdash; the key point is that the different hair cells are sensitive to different frequencies, generally in the range of 20 Hz to 20 kHz. You perceive higher frequencies as higher-pitched, and lower frequencies as lower-pitched. Every sound you hear can be decomposed into sine waves of various frequencies and amplitudes. There are Very Cool Math Reasons&trade; for this, but that's a story for another day. (Look into the Fourier Transform if you're interested!)

Enough talk. You probably want to hear one of these sine waves!

<audio controls><source src="/assets/music-theory/440Hz.mp3" type="audio/mp3"></audio>
*A 440 Hz sine wave.*{: .caption}

Okay, so that probably isn't the most pleasant sound in the world, but it is very pure. What if we play more frequencies at once? Let's pick a random<sup>[*citation needed*]</sup> frequency, like, I dunno, 712 Hz.

<audio controls><source src="/assets/music-theory/440Hz-712Hz.mp3" type="audio/mp3"></audio>
*A 440 Hz and a 712 Hz sine wave, played together.*{: .caption}

...oh my god it is *so much worse*. What did we do wrong? As it turns out, the human brain likes to hear sounds that are simple ratios of each other. If we divide 712 Hz by 440 Hz, we get a ratio of 1.618. 1.618 can't be expressed accurately by a simple ratio; in fact, it is close to the golden ratio φ, which is in some sense the [*most* irrational number](https://www.youtube.com/watch?v=CaasbfdJdJg), as it is the hardest irrational number to approximate by a simple fraction.

*I did this because I am an asshole. Sorry.*{: .caption}

To better understand what's going on, we need to talk about harmonics.

## The Harmonic Series

The reason the brain responds better to simple fractions is... well, that's a matter for psychology, but it's probably rooted in the physical properties of oscillating strings and tubes. When a tone is produced on a vibrating string or in a column of air, you don't just get a single frequency. (You probably figured this out based on the fact that real instruments don't sound like the sine waves on this page.) Instead, because there are many different solutions to the equations that govern such a vibrating object, you get a variety of *harmonics*. The first harmonic, or fundamental tone, is the lowest pitch produced, and it occurs when there are no stationary points between the ends of the object. The second harmonic, or first overtone, has a stationary point halfway between the ends. The third harmonic / second overtone has two stationary points, splitting the object into thirds. And so on. The relative strength of these different harmonics determines the *timbre* of the sound &mdash; it's what makes a guitar sound different from a piano. In terms of frequency, the overtones in a sound are integer multiples of the fundamental. If the fundamental is 440 Hz, the second harmonic is 2×440 = 800 Hz, the third harmonic is 3×440 = 1320 Hz, and so on. Higher harmonics tend to have lower amplitudes. (That's a good thing, because otherwise energy would increase without bound, thus breaking the instrument and/or forming a black hole. Whichever happens first.) If you're having trouble visualizing harmonics, there's a nice set of animations on the [Wikipedia article](https://en.wikipedia.org/w/index.php?title=Harmonic&oldid=885749464#Partials,_overtones,_and_harmonics). And here's what they sound like:

<audio controls><source src="/assets/music-theory/440Hz-harmonics.mp3" type="audio/mp3"></audio>
*A 440 Hz sine wave, and its first four overtones.*{: .caption}

This clip should sound a lot more consonant than the example with the golden ratio. Of special note is the second harmonic, which is a frequency ratio of 2 to 1, also called an *octave*. Our brain responds so well to the 2:1 ratio that, in some sense, we perceive them as the same pitch. (There are also physical reasons for this &mdash; the hairs in your ear that are sensitive to a certain frequency can also be vibrated by tones an octave away from that frequency.) As we will come to find out, this 2:1 consonance forms the foundation of our musical system. 

By the way, it is these harmonics that give the harmonic series of mathematics its name. The elements of the harmonic series &mdash; 1, 1/2, 1/3, 1/4, and so on &mdash; match the period and wavelength multiples of musical harmonics.

As a final note for this post, it is better to think of pitch on a logarithmic scale rather a linear one, since we perceive *ratios* between those frequencies, not the absolute difference between them. Consider the interval from 220 Hz to 440 Hz and the interval from 440 Hz to 880 Hz. Even though the latter is a larger jump as measured in hertz, they are both jumps by a factor of 2, so we perceive them as being equally "wide." This is also (roughly) how human vision works, and there is [evidence to suggest](http://news.mit.edu/2012/thinking-logarithmically-1005) that logarithmic thinking comes more naturally to humans than linear thinking. If you're surprised by that, well... which seems like the better deal: $5 off an $6 product, or $10 off a $1000 product?

### Conclusion

Next time, we'll dig into pitch intervals, find out why the Western musical tradition uses a 12-tone scale, and discover that our instruments don't *quite* form the perfect, simple ratios we might expect. 

{% include music-theory-series.md %}

