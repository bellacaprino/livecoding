# Tidal Cycles Documentation

The setup took me a minute, I tried to do it on my own but ultimatly ended up following the tutorial.

I went to the arpeggio section, because I love arps and want to use them. There were a lot of versions in the documentation, for example:
"c a f e" vs "<c a f e>" in the code. The brackets make it so one note is played in a cycle.

Next, i tried to play a chord, the arpeggiate it. At this point I decided I wanted to layer things so I watched a live coding video and noticed that they use "d1, d2" to use layers of things.
I figured out how to use effects and change the original sounds so I customized the arpeggio and chord sounda a little more until I liked them.

Bird time!!! added birds, now just gnna keep layer stuff.
I found a cool randomized amen cut up, Im gonna use tat for percussion. I love all my FX on the keys though and how it drones. I'm gonna add bass and some kind of snare on the 2 if i can make it work.

Patches keep trading seniority and some are cutting out, not really sure why.

Nvm i was running them wrong

Heres my final patch:

```

d1 $ sound "<birds>"
  #  delay 2.0
  # gain 0.5

d2 $ arp "<pinkyup down thumbup up>" $ n "c'maj'4 e'min"
  # sound "superpiano"
  # sustain 1.0
  # room 2.0
  # sz 1.0
  # phaserrate 4.0
  # phaserdepth 4.0
  # gain 1.0

d3 $ n "e'min"
  # sound "supermandolin"
  # legato 4

d4 $ slow 2 $ s "amencutup" <| n (shuffle 8 $ run 32) # speed "{1,2,3}%8"

d5 $ sound "sd"
  # gain 2.0

d6 $ arp "pinkyup" $ n "c'maj'4 e'min"
  # sound "superpiano"
  # sustain 0.5
  # gain 1.0
  # sz 0.6
  # room 1.0

d7 $ s "~ ~ bd ~"
  # gain 1.5

```
