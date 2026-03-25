# Prompts — 02 Album

---

**Prompt 1** | 2026-03-25 00:00

same product, album. 02. this time we'll practice two things: writing clearer copy (i got feedback that the first one didn't convey the message clearly and left them confused); and second, to try a fade-in-out slideshow on the hero image and copy.

So i was thinking of keeping the exact same layout, but we now have 3 sets of images and hero title copy, whcih will alternate in a loop every 5 seconds with a gentle ease in and out, cross fade animation. The copy should perhaps change a split second earlier and with snappier (still animated, not just swapped out), with the background image to follow. we should prefetch all images so there's no white flash while the image is loaded during transition.

i added an excalidraw screenshot that explains this in slightly more detail, and contains the 3 hero title copy ideas I have and the subtitle, which I think can stay without changing (or maybe they should change but we'll iterate on that later)

Copy from screenshot:
1. Social media for your inner circle. -> image: family friends hanging out for bbq in the backyard
2. Social media for the sovereign individual. -> image: woman smiling, taking pics of children in front of her (foregrounded, back of head)
3. Social media the way it's supposed to be. -> image: man and woman laughing happily at what they're seeing on the phone

Subtitle: When you want to keep memories and share with people close to you without paying for it with your data, privacy, and attention.

---

**Prompt 2** | 2026-03-25 00:05

let's swap the order of the animation - the text fades out together with the background, then the new background eases in first before the text catches up.

---

**Prompt 3** | 2026-03-25 00:10

now do a line break for "Social media" and whatever comes after in a newline, e.g. "for the sovereign individual" and "the way it's supposed to be" etc. these second lines are the ones that should animate in and out, leaving the words "social media" static, same as the subtitle.

---

**Prompt 4** | 2026-03-25 00:15

now look at the_way_supposed_to_be.png which is the third generated image and replace the one that was from the previous landing page (family in backyard).

---

**Prompt 5** | 2026-03-25 00:20

lets now change the animation from ease in out for the partial hero title to be the typewriter effect of the letters going away and the new letters being typed out.

take a look at the lack of reserved space for the new line in agent browser, btw, so you understand that there's a need to reserve space to prevent the text from overlapping.

increase the width given to the hero text to up to 50% of the width of the viewport (and allowing 100% in mobile). extend the black gradient mask to 50% as well to mask more and ensure the text is visible.

---

**Prompt 6** | 2026-03-25 00:30

nice! it works. please remove the blinking cursor once the full sentence has been rendered. only show it during the transition.

---

**Prompt 7** | 2026-03-25 00:35

It still shows at the end of "sovereign individual" but not the rest

---

**Prompt 8** | 2026-03-25 00:38

Oh also for the rest actually. it's nondeterministic. set interval seems like it can work, just clear it properly when the rendering has completed. is there a deterinistic way to detect that the full sentence has been redenred?

---

**Prompt 9** | 2026-03-25 00:40

line break on "without" so "... close to you" then newline "without ..."

---

**Prompt 10** | 2026-03-25 00:45

love it. well done. add new skill for ensuring that when I say to commit and push next time, you'll automatically also add any newly creatd landing pages to the index page for deployment later. then commit push :)
