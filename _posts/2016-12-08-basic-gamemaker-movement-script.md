---
layout: post
title:  Movement script, Basic GameMaker Movement Script
date:   2016-12-08
file: blog
image:
  feature: /img/posts/default_post.jpg
  class: default-post
---

## <small>Basic Movement Guide</small>
[Click here](/2016/12/08/basic-gamemaker-movement-script.html#final-result) if you just want to copy and paste the movement script.

The following Game Maker Language (GML) script is used to aid in the movement of objects within your GameMaker game, it takes in two arguments, the horizontal speed and the vertical speed.  The script also assumes that there is an object (ObjSolid) which it checks for when calculating the movement on a per step basis.
<!--more-->
The first part of the script assigns the two values passed in when calling the script, in this case I’ve used hspd and vspd to represent the horizontal and vertical speeds of the current object.

```
var hspd = argument0;
var vspd = argument1;
```

The next section of code deals with setting the horizontal movement (x-axis), first it checks to see whether there is any objects with the ObjSolid inheritance in the next x y meeting place using the place_meeting() function.  It uses the ! to invert the result, you could also consider it to mean “not equal”, so the following snippet is looking for a result that is equal to not true (false).

```
// Horizontal movement
if (!place_meeting(x + hspd, y, ObjSolid))
{
    x += hspd;
}
```

In addition to the horizontal movement we also have the vertical movement.

```
// Vertical movement
if (!place_meeting(x, y + vspd, ObjSolid))
{
    y += vspd;
}
```

Furthermore once we’ve calculated whether we can move into the next x y coordinates we then assign a value of true or false based on whether current object has been able to move or not by checking the current x and y against the x and y in the previous step.

```
// Store the move result
var moved = x != xprevious || y != yprevious;
```

Finally returning the value with

```
// Return true if we are able to move
return moved;
```

## <small>Final Result</small>
Below is the full script, feel free to copy, paste and share this.  If you feel you can improve on this then please leave a comment with the updated code and I can get this post updated accordingly.

```
/**
 * Script: ScrMovement
 * Arguments: (int) hspd
 * (int) vspd
 * Explanation: Calculates movement of player, also implements basic collision 
 * with solid object (ObjSolid).
 * 
 */
 
var hspd = argument0;
var vspd = argument1;

// Horizontal movement
if (!place_meeting(x + hspd, y, ObjSolid))
{
    x += hspd;
}

// Vertical movement
if (!place_meeting(x, y + vspd, ObjSolid))
{
    y += vspd;
}

// Store the move result
var moved = x != xprevious || y != yprevious;

// Return true if we are able to move
return moved;
```

If you’ve made it this far, thank you for reading and I hope you have learnt something or at the very least saved yourself time by using this script.  I’d like to point out that I haven’t come up with this script off of the top of my head, I have in fact seen it used by other developers and thought that it might be a good idea to share it, partly for my own use in the future.

