# Sprites
This document contains everything you need to know about sprites in an easy-to-digest way.

> ***NOTICE**: There's a whole bunch of statements here that warrant an asterisk because not everything said here is 100% correct or accurate, but for the sake of keeping things simple, these details can be considered accurate enough for our purposes.*

## What the fuck is a sprite?
Put simply, a sprite is a PNG of an object as seen in the game world. In this case, we are talking about **character sprites**. We'll talk about other kinds of sprites later.

Here are some examples:

<img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/2bf2ec51-c235-4df3-8a49-543325f3c097/df5y2ml-8e421812-588b-4fa8-ac33-d9cb0d32563e.jpg/v1/fill/w_908,h_252,q_75,strp/anime_random_characters__characters_7__sprite_by_leanboox_df5y2ml-fullview.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9MjUyIiwicGF0aCI6IlwvZlwvMmJmMmVjNTEtYzIzNS00ZGYzLThhNDktNTQzMzI1ZjNjMDk3XC9kZjV5Mm1sLThlNDIxODEyLTU4OGItNGZhOC1hYzMzLWQ5Y2IwZDMyNTYzZS5qcGciLCJ3aWR0aCI6Ijw9OTA4In1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.nHcHC-UPf0bxxGsG3DAWYscabhK3o0ZtdIq4i2rlRz8" width=100%>

*Source: [LEANBOOX from DeviantArt](https://www.deviantart.com/leanboox/art/Anime-Random-Characters-Characters-7-Sprite-916980429)*

&nbsp;

Don't let this steer you the wrong way, however. **Not all sprites are pixel art.** Sprites can come in any art style, they just happen to be the most common style for 2D indie games.

Example of non-pixel art character sprites:

<img src="https://www.pngfind.com/pngs/m/432-4323356_high-def-vector-sprites-vectorized-pokemon-hd-png.png" width=300px>

*Source: [pngfind](https://www.pngfind.com/mpng/immwhJR_high-def-vector-sprites-vectorized-pokemon-hd-png/)*

## Sprite Sheets
Okay, I lied. A **sprite sheet** is a PNG of an object or a collection of objects as seen in the game world, while a **sprite** is a slice of that sprite sheet.

Typically, a character sprite sheets contain different sprites for each character state. So for example, if a character is standing facing left, there's a sprite for that. If a character is holding a weapon, there's a sprite for that. If a character is holding a weapon while facing left, there's a sprite for that too, and they're all packed in one big sprite sheet.

<img src="https://cdn.gamedevmarket.net/wp-content/uploads/20191203175002/a3957602e81fde00a54ec207afcfe18e.png" width=100%>

*Source: [pounds from GameDev Market](https://www.gamedevmarket.net/asset/platform-character-sprite-sheet)*

In this image, you'll notice how it's been divided into segments. That's because each segment is actually a grouping for each state's **character animation**. As you can see at the top middle, the character has 2 sprites for punching, both of which are shown in-game frame-by-frame.

### Frames
Wait, what the heck is a frame?

A **frame** is basically one "frozen image" among a series of other "frozen images" that, when displayed one-by-one quickly enough, forms an animation or a video.

Games usually display a minimum of 60 frames per second. So if we use the walking animation at the top left of the image, and we want to loop back to the first sprite after 1 second, each sprite has to last 10 frames each.

It should look something like this:

<img src="https://media1.giphy.com/media/GVRemqrVxgpGruUXTs/giphy.gif?cid=6c09b95210ujk751bn31qtdtrija4v37l3v98876w53o7xff&ep=v1_gifs_search&rid=giphy.gif&ct=g" height=300px>

*Source: [BITTE EINEN FILM from GIPHY](https://giphy.com/gifs/BITTEEINENFILM-GVRemqrVxgpGruUXTs)*

As you can see, the character cycles between "Student 03" to "Student 05" while walking, while "Student 01" is the idle/standing animation and "Student 02" is the transition from standing to walking. All 5 of these frames, can be found in a single sprite sheet.

# How do I make a character sprite?


## Tools
First, you'll need to figure out what tools you'll use depending on the art style you want to achieve.

### Raster Graphics
Put simply, a raster image is your typical JPEG, PNG, GIF, or whatever else. These are very versatile in that they can be displayed just about anywhere because everyone and their dog supports these formats. They're light on the computer and are relatively easy to make, but making changes are difficult as they're effectively permanent; you can only draw over what's already there.

Some of the most common choices for making raster-based art are [Photoshop](https://www.adobe.com/ph_en/products/photoshop/landpa.html) and [Krita](https://store.steampowered.com/app/280680/Krita/), while [Paint.NET](https://www.getpaint.net/) and [GIMP](https://www.gimp.org/), or even just Microsoft Paint are also good free options depending on what you're making.

If you have no idea what you're doing (yet), or you just don't care, it's best that you start here. It's a format you're already familiar with, so why look elsewhere? You can always change formats later.

> If you're an artist working on PSI, we're using this.

#### Pixel Art
Basically, pixel art is just a really small raster image. You use what little space you have to show as much detail as you can. This sacrifices small details in exchange for ease-to-make and in-game performance.

If you want to make pixel art sprites, [Pixel Studio](https://store.steampowered.com/app/1204050/Pixel_Studio__pixel_art_editor/) is a great free option available in [Steam](https://steampowered.com/). If you want a more complete option, [Aseprite](https://store.steampowered.com/app/431730/Aseprite/) is also available on Steam for an affordable price. Though, you can of course just use the same tools used to make **raster graphics**. After all, pixel art is just a really small raster image.

### Vector Graphics

<img src="https://cdn.firespring.com/images/e990a5e9-5c64-4a26-b6b2-3b603999c910.jpg" height=300px>

Conversely to raster graphics, vector graphics is infinitely scalable. That means that you can zoom in as closely as you want and it won't become blurry or pixelated. In editing, vector graphics can also be far easier to work with if you're making changes on an existing image.

In raster, you show the computer what a circle looks like. In vector, you tell the computer how to make a circle and it shows it for you.

Of course, this comes at a performance cost. Vector graphics are made up of nodes that connect to each other using the mathematical equations you told them to recreate. So the more nodes there are, and the more complex these equations are, the harder they are to render.

Some of the most common choices for vector graphics are [Adobe Illustator](https://www.adobe.com/products/illustrator.html), [Affinity Designer](https://affinity.serif.com/en-us/designer/), and [Clip Studio Paint](https://www.clipstudio.net/en/), though all of these do cost money to use. If you want something free and open-source, try [Inkscape](https://inkscape.org/).

If your game often zooms in close and you want to infinitely scale without losing detail, or if your game somehow makes use of vector nodes, vector graphics may be the format best fit for your game. Although, be prepared to make optimizations to minimize its performance impact.

## Preparations and Prerequisites