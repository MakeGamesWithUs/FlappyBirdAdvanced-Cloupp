Creating an Update Loop
=============

So far we have only made the character move vertically. Now we want to make him
move to the right, so he can progress through the level. Unlike jumping, we want the
character to be constantly moving on the X axis.

For this sort of logic, games typically use an "update loop." What happens is that some
code is run really fast - up to 60 times per second! That code usually checks things like
player health, whether enemies have died, or whether something should move!

In order to create an update loop, you need to add a new method. Below the
closing bracket of your ```touchBegan``` method, but before the ```@end```,
add the following:

	- (void)update:(CCTime)delta
	{
		// this will be run every frame.
		// delta is the time that has elapsed since the last time it was run.
	}

Making the Character Move
=============

Now that we have an update loop, making the character move is easy. We just need to
set the horizontal velocity to 80 and not change the vertical velocity.

To do that, in your new ```update``` method, add:

	character.physicsBody.velocity = ccp(80, character.physicsBody.velocity.y);
