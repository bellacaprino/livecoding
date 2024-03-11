# Hydra Documentation

Here is a Hydra patch that I made - I wanted to combine the camera with cool effects

I was curious about the blend effect, and I want to combine it with a more complicated patch for cool video manipulation!!

I got something pretty cool but I want more!!

```
s0.initCam()

src(s0).out(o0) // render the webcam to output o0

osc(9,0.1,1).diff(osc(13,0.5,5)).out(o1)

src(o0).diff(o1).out(o2) 

render(o2) 

```
It seems like in order to blend things I use a seperate syntax instead of doing it inside the previous syntaxes.

Huzzah! This is very cool, now I can blend webcam footage with cool visuals!! I edited a preset to do this, now I'm going to try other cool things.

```

s0.initCam()
noise(3,0.3,3).thresh(0.3,0.03).diff(o3,0.3).out(o1)
src(s0).diff(o0).blend(o1).out(o3)
voronoi(33,3,30).rotate(3,0.3,0).modulateScale(o2,0.3).color(-3,3,0).brightness(3).out(o0)
shape(30,0.3,1).invert(({time})=>Math.sin(time)*3).out(o2)

render(o3)

```

Now I want an image as well

```

s0.initCam()

s1.initImage("https://img.thedailybeast.com/image/upload/c_crop,d_placeholder_euli9k,h_1439,w_2560,x_0,y_0/dpr_2.0/c_limit,w_740/fl_lossy,q_auto/v1492203936/articles/2013/12/19/this-is-how-an-episode-of-cartoon-network-s-adventure-time-is-made/131218-goldstein-adventure-tease_c6znaz")
src(s1).diff(o3,0.3).out(o1)
src(s0).diff(o0).blend(o1).out(o3)
voronoi(33,3,30).rotate(3,0.3,0).modulateScale(o2,0.3).color(-3,3,0).brightness(3).out(o0)
shape(30,0.3,1).invert(({time})=>Math.sin(time)*3).out(o2)

render(o3)

```

This is a lot of fun! Documentation for Hydra is super helpful!! I'm def gonna keep getting better at this, I think live coding visuals might be my calling !!! :))