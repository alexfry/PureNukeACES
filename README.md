As part of the process of chasing down some technical gremlins in an ACES colour pipeline, I've recently had the need to develop a pure Nuke implementation of the ACES RRT and P3D60 ODT. This is a line by line reimplentation of the CTL code in ACES 1.0.3.
![Screenshot]\(https://static1.squarespace.com/static/52d3c851e4b067bcd605eacd/t/583e3f182994cabd627efe0f/1480474419962/Screenshot+2016-11-30+13.50.54.png?format=1500w)
These nodes serve two purposes. They provide a way to render code based versions of the RRT and ODT in Nuke, with a 100% match to a pure CTL implementation. And provide a much easier way to visualise and understand the guts of the ACES Display Transform system.

![Screenshot]\(https://static1.squarespace.com/static/52d3c851e4b067bcd605eacd/t/583e6831579fb3beb5898e62/1480484929556/?format=1500w)

![Screenshot]\(https://static1.squarespace.com/static/52d3c851e4b067bcd605eacd/t/583e684f579fb3beb5898fb9/1480484952739/?format=1500w)

They're not as fast or flexible as using the LUTs within the OCIO config, but they're a few orders of magnitude faster than ctlrender, and much easier to integrate into a Nuke workflow.

With normally exposed images, especially from live action cameras, you're unlikely to see any values that render differently to the OCIO config, but with CG images containing extreme intensity and saturation you will see more pleasing roll off and desaturation.

Right now I've only implemented the RRT and  P3D60 ODT, and only in the forward direction. But in the future I may implement more.

![Screenshot]\(https://static1.squarespace.com/static/52d3c851e4b067bcd605eacd/t/58450d4a579fb3ad1b13a93f/1480920448265/?format=1500w)

![Screenshot]\(https://static1.squarespace.com/static/52d3c851e4b067bcd605eacd/t/58450d9a579fb3ad1b13ab9f/1480920524890/?format=1500w) 
