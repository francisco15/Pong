# Mini-project development process

1. Add code to the program template that draws a ball moving across the Pong table. We recommend that you add the positional update for the ball to the draw handler as shown in the second part of the "Motion" video.

2. Add code to the function 𝚜𝚙𝚊𝚠𝚗_𝚋𝚊𝚕𝚕 that spawns a ball in the middle of the table and assigns the ball a fixed velocity (for now). Ignore the parameter 𝚍𝚒𝚛𝚎𝚌𝚝𝚒𝚘𝚗 at this point.

3. Add a call to 𝚜𝚙𝚊𝚠𝚗_𝚋𝚊𝚕𝚕 in the function 𝚗𝚎𝚠_𝚐𝚊𝚖𝚎 which starts a game of Pong. Note that the program template also includes an initial call to 𝚗𝚎𝚠_𝚐𝚊𝚖𝚎 in the main body of your program to get a game going immediately.

4. Modify your code such that the ball collides with and bounces off of the top and bottom walls. Experiment with different hard-coded initial velocities to test your code.

5. Add randomization to the velocity in 𝚜𝚙𝚊𝚠𝚗_𝚋𝚊𝚕𝚕(𝚍𝚒𝚛𝚎𝚌𝚝𝚒𝚘𝚗) The velocity of the ball should be upwards and towards the right if 𝚍𝚒𝚛𝚎𝚌𝚝𝚒𝚘𝚗 == 𝚁𝙸𝙶𝙷𝚃 and upwards and towards the left if 𝚍𝚒𝚛𝚎𝚌𝚝𝚒𝚘𝚗 == 𝙻𝙴𝙵𝚃. The exact values for the horizontal and vertical components of this velocity should be generated using 𝚛𝚊𝚗𝚍𝚘𝚖.𝚛𝚊𝚗𝚍𝚛𝚊𝚗𝚐𝚎(). For the horizontal velocity, we suggest a speed of around 𝚛𝚊𝚗𝚍𝚘𝚖.𝚛𝚊𝚗𝚍𝚛𝚊𝚗𝚐𝚎(𝟷𝟸𝟶, 𝟸𝟺𝟶) pixels per second. For the vertical velocity, we suggest a speed of around 𝚛𝚊𝚗𝚍𝚘𝚖.𝚛𝚊𝚗𝚍𝚛𝚊𝚗𝚐𝚎(𝟼𝟶, 𝟷𝟾𝟶) pixels per second. (You will need to set the signs of velocities appropriately.)

6. Add code to the draw handler that tests whether the ball touches/collides with the left and right gutters. (Remember that the gutters are offset from the left and right edges of the canvas by the width of the paddle as described in the "Pong" video.) When the ball touches a gutter, use either 𝚜𝚙𝚊𝚠𝚗_𝚋𝚊𝚕𝚕(𝙻𝙴𝙵𝚃) or 𝚜𝚙𝚊𝚠𝚗_𝚋𝚊𝚕𝚕(𝚁𝙸𝙶𝙷𝚃) to respawn the ball in the center of the table headed towards the opposite gutter.

7. Next, add code that draws the left and right paddles in their respective gutters. The vertical positions of these two paddles should depend on two global variables. (In the template, the variables were 𝚙𝚊𝚍𝚍𝚕𝚎𝟷_𝚙𝚘𝚜 and 𝚙𝚊𝚍𝚍𝚕𝚎𝟸_𝚙𝚘𝚜.)

8. Add code that modifies the values of these vertical positions via an update in the draw handler. The update should reference two global variables that contain the vertical velocities of the paddles. (In the template, the variables were 𝚙𝚊𝚍𝚍𝚕𝚎𝟷_𝚟𝚎𝚕 and 𝚙𝚊𝚍𝚍𝚕𝚎𝟸_𝚟𝚎𝚕.)

9. Update the values of these two vertical velocities using key handlers. The "w" and "s" keys should control the vertical velocity of the left paddle while the "Up arrow" and "Down arrow" key should control the velocity of the right paddle. In our version of Pong, the left paddle moves up at a constant velocity if the "w" key is pressed and moves down at a constant velocity if the "s" is pressed and is motionless if neither is pressed. (The motion if both are pressed is up to you.) To achieve this effect, you will need to use both a keydown and a keyup handler to increase/decrease the vertical velocity in an appropriate manner.

10. Restrict your paddles to stay entirely on the canvas by adding a check before you update the paddles' vertical positions in the draw handler. In particular, test whether the current update for a paddle's position will move part of the paddle off of the screen. If it does, don't allow the update.

11. Modify your collision code for the left and right gutters in step 6 to check whether the ball is actually striking a paddle when it touches a gutter. If so, reflect the ball back into play. This collision model eliminates the possibility of the ball striking the edge of the paddle and greatly simplifies your collision/reflection code.

12. To moderately increase the difficulty of your game, increase the velocity of the ball by 10% each time it strikes a paddle.

13. Add scoring to the game as shown in the Pong video lecture. Each time the ball strikes the left or right gutter (but not a paddle), the opposite player receives a point and ball is respawned appropriately.

14. Finally, add code to 𝚗𝚎𝚠_𝚐𝚊𝚖𝚎 which resets the score before calling 𝚜𝚙𝚊𝚠𝚗_𝚋𝚊𝚕𝚕. Add a "Restart" button that calls 𝚗𝚎𝚠_𝚐𝚊𝚖𝚎 to reset the score and relaunch the ball.
