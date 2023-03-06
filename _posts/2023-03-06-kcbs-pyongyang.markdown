---
layout: post
title:  "Listening to KCBS Pyongyang"
---

Software Defined Radio is an amazing thing.

Wanna listen to some Japanese radio?
The original [webSDR](http://websdr.org/) is pretty dead in Asia, and the few SDRs that are there only have very limited frequency ranges (only airport comms for example).

But: the [KiwiSDR project](http://kiwisdr.com/) has a [similiar map](http://rx.linkfanel.net/), and there are plenty of receivers in Japan and 2 in South Korea.

So I was browsing around and noticed that some stations were being jammed.
When you google the frequency you get to the nice site [Shortwave Schedule](https://shortwaveschedule.com/index.php?now) which also lets you filter broadcasts by language.
One of these languages is "Noise jamming" and all the broadcasts come from [Kujang](https://www.northkoreatech.org/2011/04/29/kujang-shortwave-transmitter-site/).
From the information on the website it seems they don't transmit anything else there, so maybe it's a military installation?

Anyway, if i can hear the jammer, surely I can hear regular stations too.
So I filtered the schedule by Korean language and picked the station with the highest transmit power in the North.
Pyongyang BS sending 1500kW on 657kHz and 451 km away from [the webSDR](http://hik.iptime.org:8075).

Terrible reception, humming and buzzing.
Well it's a LW broadcast, let's try the next one.

[KCBS Pyongyang with 100kW on 3250kHz](http://hik.iptime.org:8075/?f=3250.00amz10)

They also transmit on 6100kHz but China Radio International can be heard at the same time, I wonder if this is intentional?

That worked but then at 18:00 UTC they turned off the transmitter!
According to the Schedule it's a 2 hour break from 03:00-05:00 Seoul time.

[Pyongyang BS](http://hik.iptime.org:8075/?f=3320.00amz10) (again) is right next to it on 3320kHz but only with 50kW.
But this time it's loud and much clearer.

[KCBS Pyongyang can also be received digitally](http://sdr-swl.p.sdrotg.com/?f=3205.00drmz11) with higher audio quality but the playback keeps dropping out or it starts stuttering.

![Gone](/assets/images/kcbs-off.jpg)
