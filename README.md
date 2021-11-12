SignalRGB_CustomScript

 ## Table of Contents
  - [Description](#Description)
  - [License](#License)
  - [Contributing](#Contributing)
  - [Questions](#Questions)

    ## Description
    A custom light script designed using HTML Canvas and the SignalRGB engine. Inspired by 3D Perlin Noise.
  
    This web application was created with HTML, CSS, HTML Canvas, and the Signal RGB engine. Used custom npm library to generate perlin noise, found here:

    https://www.npmjs.com/package/perlin-noise-3d

    ## Process
    This particular project was done using a program created by WhirlwindFX, known as Signal RGB. The program is available to download and lest users choose from preset themes to illuminate their tech that is able to connect to your PC and display RGB colors. To those who wish, the program allows users to create their own theme. In order for the engine to work, scripts are created using HTML files, and more specifically, created using the Canvas object. Then you can place the HTML file into the engine itself and see your effect in the library. This process lets the user have seemingly endless possibilities of light effects to have for their own set ups. From simple rainbow effects, to more intricate particle and lighting effects, SignalRGB is an amazingly fun program to work with.

    I wasn't satisfied with just creating something as simple as a rainbow lightshow, however. This is where Perlin Noise comes in. If you want to learn more about it, check out this link:

    https://www.youtube.com/watch?v=Qf4dIN99e2w

    Essentially, perlin noise is used to create realistic textures such as clouds or mist, using an algorithim that generates random numbers. But rather than these numbers being completely random, values are interpolated, or smoothed out with each other. The result is an image that is much smoother in appearance than if the values generated were completely random. It's a bit of a difficult concept to comprehend honestly. But instead of creating my own algorithim to simulate the perlin noise effect, I used a library that had already been created for Javascript. You can find that library for NPM here:
    
    https://www.npmjs.com/package/perlin-noise-3d

    ### Functionality
    In order for this whole project to work, I needed to build and HTML file with the Canvas object, since that is what SignalRGB uses. The canvas is a very fun and interesting way to practice coding and finding ways to work your brain in a different way that is much more rewarding than simply displaying a div on screen (I made a ball that bounced around the screen for example). So with this in mind, I could create some form of perlin noise. To do this, I used the npm library I mentioned above, which gave instructions for how to use it. When you want a new instance of the noise object, you simply call it's get function. This returns x, y, and z coordinates (you can limit it to x and y, but introducing the z dimension was much more pleasing to look at). With these coordinates, you can place a pixel at that location on the canvas. 

    In order for all this to work, you need to create an update loop and have it being called by itself. This insures that everytime something runs, it runs over and over on an infinite loop. In this loop, I created a nested loop to fill out the canvas using the coordinates that were given. It looks like this:

     for(let y = 0; y < height / scale; y++ ) {                  // Nested loop generates a row of pixels (x) for every column (y)
            for(let x = 0; x < width / scale; x++ ) {
                let r = noise.get(x , y , z );          // noise.get() returns x, y, and z coordinate 
                let g = noise2.get(x , y , z );
                let b = noise3.get(x , y , z );

    So for every column (y), you fill out a row of pixels (x). This populates the entire canvas. The r, g, and b values are used for the respective color channels and each have random coordinates and values. After this, you can use the fill function provided by the canvas object to color in the screen. To do this, I used the rgb attribute.

    ctx.fillStyle = "rgb(" + r + "," + g + "," + b + ")";

    One interesting thing about SignalRGB is it lets users create ways to have other users scale parts of their lightscript. If you wanted to have the colors change faster for example, you can define a "speed" parameter in the head of the file, and then set it's default or min and max values. Then you can insert the speed property into your Javascript the same as any other variable. 

    I created parameters for speed, scale (how zoomed in you are essentially), and the color intensities. The color intensities were scaled by having the color value multiplied by the scaled value of the user. You can have very intense greens, or very subtle greens, to no greens at all. Each color has their own respective scalars (rMultiplier, gMultiplier, and bMultiplier)

    ## License
    [MIT](https://opensource.org/licenses/MIT)

    ## Contributing
    [SignalRGB](https://www.whirlwindfx.com/pages/signalrgb)
    [Perlin Noise Generator](https://www.npmjs.com/package/perlin-noise-3d)


    ## Questions
    [GitHub: Fatmoogle](https://github.com/Fatmoogle)
    [Email: alexvar93@gmail.com](alexvar93@gmail.com)
    Feel free to reach out to me with any questions! Happy Hacking!