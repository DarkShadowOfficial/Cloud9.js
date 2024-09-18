# Cloud9.js
Cloud9.js is a flexible video game and 2d graphics framework for JavaScript, which performs the bulk of necessary procedures for building a game.

## Documentation:
After implementing the script into your HTML project, go to your script.js file, or whatever your main JS file is.

To initialize the Cloud:

```
let cloud = new Cloud(*optional false boolean*) // Create cloud variable. The *false* that you pass in makes it so the screen doesn't clear after animation, allowing for drawing.
cloud.InitializeScreen(500, 600, "blue") // Displays the screen with 500x600 dimensions, and a blue background. The color defaults to white, but this can be changed.
cloud.InitMouse(); // Optional. This is only for programs which require mouse interactions.
```

To create a new character, or object:

```
cloud.CreateCharacter(*name*, *draw function with vars as a parameter*, *behavior function with vars as the parameter*, *vars?*);
/* The name of the character allows quick and easy access to run the character. The draw function parameter is to actually draw the character/object. The behavior function is to give it action and behavior, as in the name. Vars is an optional parameter which defaults to an x and y value, positioned at the center of the screen. If you choose to create customized variables for the character, the x and y properties are REQUIRED to function. */
```

To animate a specific character based on their behavior:

```
cloud.RunCharacter(*name*); // Pass in the name of the character, which you should have defined as a parameter earlier, and it will both draw and animate the character.
```

To run every character created:

```
cloud.RunAll();
```

This is usually used in an animation loop:

```
let animate = () => {
  cloud.RunAll(); // Or run a specific character, depending on your usage.
  requestAnimationFrame(animate);
}
animate();
```

If you want to create numerous characters with the same behavior and similar characteristics, just use the Cloud.CreateCharacterClass() method:

```
cloud.CreateCharacterClass(*class name*, *etc.*)
/* The *etc.* is simply just the same parameters as from the Cloud.CreateCharacter() method, shown above. The only difference is that *class name* defines a broad class of characters/objects, while a regular *name* is simply for one specific object. */
```

To create a character from a class:

```
cloud.CreateCharacterFromClass(*class name*, *specific variables*) // Specific variables are variables unique to this specific character, such as color, speed, etc., depending on your usage.
```

Thank you for trying Cloud9.js for your animation and computer graphics!
