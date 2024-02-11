# The New
I'm gonna be honest - I had a lot of trouble processing this text. I read it several times. So if my understanding of the concepts aren't the best - thats why.

I learned about the #Occupy movement, and how its leaderhsip used no heiarchial structures. I like that it is decentralized, and how it uses horizonal organization.

I also learned about the LAMC, which was one of the first groups to explore the intersection of comoputor technology and music composition. I thought it was cool how they did the first expierements routing between computors. They recognized the importance of designing collaborative technology.


# The Old
I am familliar with some forms of organization provided as examples and how they function. Such as Authoritarian states, Democratic States, Symphony Orchestra, Bands and etc. 

I am familliar with the concept that technological development drives political change. The article used the examples of the industrial revoltion which prompted society to organize society into heirarchal structions to enhance the production of goods.


# Patch

started with this based on the arp in the notes for week 2 but it wasnt working: 

``stack [
note (arp "updown" <f'maj7 ab'maj7 g'min7 f'maj7>") # s "space" ]``\

ah was missing an outer quotation
I'm running through sounds rn - i made a masterlist

trying to stack sounds

``stack [
note (arp "updown" "<f'maj7 ab'maj7 g'min7 f'maj7>") # s "gab",
# s bottle ]``

it reall annoys me how theres a break in between the chords every round in some circumstances but not in others

jeez all these sounds are popping

then i had this
``stack [
note (arp "updown" "<f'maj7 a'maj7>") # s "moog" # pan sine, 
s "bottle*4" #pan square, 
s "bubble" #gain 1.2,
s "bd bd bd bd" # gain 1.1"
]``

which has a syntax error and im not sure why

i got rid of the comma to add the snare but i want a snare and its worked before so veyr weird

``stack [
note (arp "updown" "<f'maj7 a'maj7>") # s "moog" # pan sine,
s "bottle*4" #pan square, 
s "bubble" #gain 1.2,
s "bd bd bd bd" # gain 1.1
]``

it just doesnt like when i stack drums within a list so i made two and added bird sounds

``stack [
note (arp "updown" "<f'maj7 a'maj7>") # s "moog" # pan sine,
s "bottle*4" #pan square, 
s "bubble" #gain 1.2,
s "hh hh hh hh hh hh" # gain 1.1,
s " bd bd? ~ sd ~ ~",
s "birds" # gain 0.5
]``

```stack [
note (arp "updown" "<f'maj7 a'maj7>") # s "moog" # pan sine,
note (arp "downup" "<f'maj7 a'maj7>") # s "ukulele" # pan cosine,
s "bottle*4" #pan square, 
s "bubble" #gain 1.2,
s "hh hh hh hh hh hh" # gain 1.1,
s " bd bd? ~ sd ~ ~",
s "birds" # gain 0.5``
]``````

added some counterpoint, and a good beat that matches the arp. and calling it good :)



