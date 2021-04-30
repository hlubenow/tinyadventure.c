#### Adventure Movement

For many, many years, I always wondered, how the movement in adventure games was managed.
From a starting room, you can walk to a second room, and walk back to the first room. There may also be the directions "up" and "down". How is this done?

The rooms should point to each other. This leads to a web-like structure. In [this video](https://www.youtube.com/watch?v=8CDePunJlck) about Python, the lecturer suggests a "Room" class, and in this class a dictionary "self.exits", like this:

    self.exits = {"n" : "living room", "u" : "bed room", "s" : "garden"}

That would make the locations point to each other in a very comprehendable fashion.
Then I thought, if you have to save memory (like on an 8 bit computer), you could also store this in a 2D array: Each room has a room number, starting with 1, and it has its own line in the array. The columns of the line represent the directions. So if the directions are "n", "e", "s", "w", there are four columns in each line. (And one line for each room.)
And at each direction column, the number of the room, to which the direction movement leads, is stored.
If the direction doesn't lead to any room, "0" is stored in the array line (in the matrix).
There are two examples "move_example.py" and "move_example.c" here, to show, how this can be done.

Even more compact would be strings like "#C#E" using ASCII-values to store room numbers.

License is GNU GPL 3 (or above).
