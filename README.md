As part of the process of chasing down some technical gremlins in an ACES colour pipeline, I've recently had the need to develop a pure Nuke implementation of the ACES RRT and P3D60 ODT. This is a line by line reimplentation of the CTL code in ACES 1.0.3.
Screenshot 2016-11-30 13.50.54.png
These nodes serve two purposes. They provide a way to render code based versions of the RRT and ODT in Nuke, with a 100% match to a pure CTL implementation. And provide a much easier way to visualise and understand the guts of the ACES Display Transform system.


They're not as fast or flexible as using the LUTs within the OCIO config, but they're a few orders of magnitude faster than ctlrender, and much easier to integrate into a Nuke workflow.

With normally exposed images, especially from live action cameras, you're unlikely to see any values that render differently to the OCIO config, but with CG images containing extreme intensity and saturation you will see more pleasing roll off and desaturation.

Right now I've only implemented the RRT and  P3D60 ODT, and only in the forward direction. But in the future I may implement more.
