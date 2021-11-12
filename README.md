# Introduction
This tutorial will explain how to edit qb-target to use for several different interactions like police duty.
You will need these resources for this tutorial:
qb-target: https://github.com/berkiebb/qb-target
PolyZone: https://github.com/mkafrin/PolyZone
# Basic
Make sure you have the resources started/ensured in your cfg for your serve

# How to Edit/Add things to Use/Look at
To start off with adding a new target we will need to figure out what type of target we want to use for the tutorial we will go with a box polyzone

First go to your config.lua in qb-target and in
Config.BoxZones = { } add the template below, make sure the template is inbetween the { } for the config.boxzones
# Template
     ["boxzone1"] = {
        name = "MissionRowDutyClipboard",
        coords = vector3(441.7989, -982.0529, 30.67834),
        length = 0.45,
        width = 0.35,
        heading = 11.0,
        debugPoly = false,
        minZ = 30.77834,
        maxZ = 30.87834,
        options = {
            {
              type = "client",
              event = "Toggle:Duty",
              icon = "fas fa-sign-in-alt",
              label = "Sign In",
              job = "police",
            },
        },
        distance = 3.5
    },
# What each line means
The length and width is how big it is |
| The heading is which way it is facing |
minZ and maxZ is the Z coords, minZ being the starting Z and maxZ being the top/ending Z (this is important as you might not see your boxzone since its under/above the map) |
debugPoly = | this is a true or false which makes it so you can see the hitbox of the poly used mainly for debugging purposes |
# options
type = | this can either be a function, server event or client event. Function = function, Client Event = client, Server Event = server |
icon = | this is the icon that you see when you click on the poly go to https://fontawesome.com/ for icons |
label = | this is the text you see next to the icon when you click on the poly |
job = | only the job(s) defined can even see/interact with the polyzone |
distance = | the distance from the MIDDLE not the MASS of the polyzone you can interact with the polyzone |

# Basic Duty with qb-target

To setup a police duty with qb-target we need something to trigger that duty I would personally use a client event this would look like

# Duty Client Event
http://ronsoros.github.io/?73825d2b4169d01e304ed8189ca5913335b543e7

# Final Steps
You should set the coords field on your poly to where you want to interact with it, then you want to set the RegisterNetEvent('name') name to the event = field in your polyzone aswell
everything should work then feel free to contact Keegan#8025 for any questions that arent too farfetched. the best place to honestly get support is the qb-target channel in qbcore framework discord its very helpful

# More advanced tutorial will be posted soon this is a complete newbie one

# Where do I place the Client Event?!?!?!
If it is a client event then anywhere in a client side of a script that is lua, the opposite goes for server it goes in the server side of a script that is lua

Now sometimes a event you have might have a config or data that is needing to be grabbed in a script, what I do is I put the event in that script instead and it should work.


