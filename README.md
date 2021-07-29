# PDT-HAAR-Guide
Short guide on setting up and conducting HAAR (Helicopter Air-to-Air Refueling) with the Hatchet H-60 mod.
Video: https://youtu.be/8r1eApOdSSI

### All code used can be found in the "Code.md" file.

### Mission setup:
There are three things you need for HAAR (Helicopter Air-to-Air Refueling), a compatible helicopter (one with a fuel probe), a plane (I'll be using the one provided), and a Game Logic.
If you do not want a tracking marker don't use a Game Logic.

Steps:
1) Place a compatible helicopter.
2) Place a tanker in the bottom-left corner of the map and give it 4 waypoints. Put a "move" waypoint in the bottom-right corner, top-right corner, and top-left corner, then place a "cycle" waypoint in the bottom-left corner.
3) In the tankers init paste the "Tanker init" code (see the Code.md file).

Optional: set the tanker's variable name to "PDT_Tanker" or a variable name of your choice.
If you don't want a tracking marker you're done. Preview the mission and skip to the "Refueling" section.

### Game Logic setup:
The Game Logic is how I'm going to setup a tracking marker, again, skip this step if you don't want it.

Steps:
1) Place a Game Logic.
2) In the Game Logic's init paste the "Game Logic init" code (see the Code.md file).
3) Done. Preview the mission.

### Refueling:
Once you're done with the setup preview the mission and fly to the tanker. You should see a basket floating behind it.

Steps:
1) Extend your fuel probe. To do this look at the FMS (rectangle screen next to your left knee) and navigate to the "Fuel" tab. Find the "Move probe" option (top-right) and press it.
2) Move closer to the basket and poke it with your fuel probe. When you're close enough it will attach to your probe.
3) Maintain speed and altitude until you're done refueling.
4) Disconnect from the basket. Maintain altitude and decrease speed until the basket disconnects.
5) Retract your fuel probe. Do the same thing you did to extend it but in reverse.

Done. Congratulations, if you did it correctly you just successfully conducted HAAR.

### Using other planes:
It is possible to use other planes to conduct HAAR, the C-130 from the USAF mod is one of them. To set this up you just need to replace the provided tanker with the C-130 and add a bit more code to it (see the Code.md file).

If you just want to use another plane and don't care about how the rope or basket is attached use the "Alternate plane basic" init code.
