# Sprites
This document contains everything you need to know about sprites in an easy-to-digest way.

> **NOTICE**: There's a whole bunch of statements here that warrant an asterisk ( \* ) because not everything said here is 100% correct or accurate, but for the sake of keeping things simple, these details can be considered accurate enough for our purposes.

# What on earth is a sprite?
Put simply, a sprite is a PNG of an object as seen in the game world. In this case, we are talking about **character sprites**. We'll talk about other kinds of sprites later.

Here are some examples:

<img src="https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/2bf2ec51-c235-4df3-8a49-543325f3c097/df5y2ml-8e421812-588b-4fa8-ac33-d9cb0d32563e.jpg/v1/fill/w_908,h_252,q_75,strp/anime_random_characters__characters_7__sprite_by_leanboox_df5y2ml-fullview.jpg?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7ImhlaWdodCI6Ijw9MjUyIiwicGF0aCI6IlwvZlwvMmJmMmVjNTEtYzIzNS00ZGYzLThhNDktNTQzMzI1ZjNjMDk3XC9kZjV5Mm1sLThlNDIxODEyLTU4OGItNGZhOC1hYzMzLWQ5Y2IwZDMyNTYzZS5qcGciLCJ3aWR0aCI6Ijw9OTA4In1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmltYWdlLm9wZXJhdGlvbnMiXX0.nHcHC-UPf0bxxGsG3DAWYscabhK3o0ZtdIq4i2rlRz8" width=100%>

*Source: [LEANBOOX from DeviantArt](https://www.deviantart.com/leanboox/art/Anime-Random-Characters-Characters-7-Sprite-916980429)*

Don't let this steer you the wrong way, however. **Not all sprites are pixel art.** Sprites can come in any art style, they just happen to be the most common style for 2D indie games.

Example of non-pixel art character sprites:

<img src="https://www.pngfind.com/pngs/m/432-4323356_high-def-vector-sprites-vectorized-pokemon-hd-png.png" width=40%>

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

<img src="https://media1.giphy.com/media/GVRemqrVxgpGruUXTs/giphy.gif?cid=6c09b95210ujk751bn31qtdtrija4v37l3v98876w53o7xff&ep=v1_gifs_search&rid=giphy.gif&ct=g" width=35%>

*Source: [BITTE EINEN FILM from GIPHY](https://giphy.com/gifs/BITTEEINENFILM-GVRemqrVxgpGruUXTs)*

As you can see, the character cycles between "Student 03" to "Student 05" while walking, while "Student 01" is the idle/standing animation and "Student 02" is the transition from standing to walking. All 5 of these frames, can be found in a single sprite sheet.

# Tools
Before you can create sprites, you'll need to figure out what tools you'll use depending on the art style you want to achieve.

## Raster Graphics
Put simply, a raster image is your typical JPEG, PNG, GIF, or whatever else. These are very versatile in that they can be displayed just about anywhere because everyone and their dog supports these formats. They're light on the computer and are relatively easy to make, but making changes are difficult as they're effectively permanent; you can only draw over what's already there.

Some of the most common choices for making raster-based art are [Photoshop](https://www.adobe.com/ph_en/products/photoshop/landpa.html) and [Krita](https://store.steampowered.com/app/280680/Krita/), while [Paint.NET](https://www.getpaint.net/) and [GIMP](https://www.gimp.org/), or even just Microsoft Paint are also good free options depending on what you're making.

If you have no idea what you're doing (yet), or you just don't care, it's best that you start here. It's a format you're already familiar with, so why look elsewhere? You can always change formats later.

> We use this in [Project Sentient Island](https://github.com/DefinitelyRus/ProjectSentientIntelligence) (PSI).

### Pixel Art
Basically, pixel art is just a really small raster image. You use what little space you have to show as much detail as you can. This sacrifices small details in exchange for ease-to-make and in-game performance.

If this sounds like a great fit for your project, here are some options to get you started:
- [Pixel Studio](https://store.steampowered.com/app/1204050/Pixel_Studio__pixel_art_editor/) (One-time Payment on Steam, Microsoft Store, and Google Play Store)
- [Aseprite](https://store.steampowered.com/app/431730/Aseprite/) (One-time Payment on Steam and itch.io, Open-source)

You can of course just use any of the same tools used to make **raster graphics**. It won't be as convenient though.

> We use this in Project Ui Beam (PUB).

## Vector Graphics

<img src="https://cdn.firespring.com/images/e990a5e9-5c64-4a26-b6b2-3b603999c910.jpg" width=70%>

*Source: [Michael Christensen from ABC Printing Company](https://abcprint.com/about-us/news-archive.html/article/2021/07/08/raster-vs-vector-images-what-s-the-difference-)*

Conversely to raster graphics, vector graphics is infinitely scalable. That means that you can zoom in as closely as you want and it won't become blurry or pixelated. In editing, vector graphics can also be far easier to work with if you're making changes on an existing image.

In raster, you show the computer what a circle looks like. In vector, you tell the computer how to make a circle and it shows it for you.

Of course, this comes at a performance cost. Vector graphics are made up of nodes that connect to each other using the mathematical equations you told them to recreate. So the more nodes there are, and the more complex these equations are, the harder they are to render.

If your game often zooms in close and you want to infinitely scale without losing detail, or if your game somehow makes use of vector nodes, vector graphics may be the format best fit for your game. Although, be prepared to make optimizations to minimize its performance impact.

But! You can always reap the benefits of vector graphics while editing while having the in-game performance of raster graphics by exporting your vector image to raster! It won't be infinitely scalable anymore in-game, but you can just export to a larger resolution if you need that extra detail.

If this sounds like the perfect solution for you, here are some of the most common choices for vector graphics:
- [Adobe Illustator](https://www.adobe.com/products/illustrator.html) (Subscription Only)
- [Affinity Designer](https://affinity.serif.com/en-us/designer/) (One-time Payment)
- [Clip Studio Paint](https://www.clipstudio.net/en/) (Limited Free, One-time Payment, Subscription)
- [Inkscape](https://inkscape.org/) (Free, Open-source)

> **NOTICE**: For the rest of this document, we will assume the use of **raster graphics** both in creation and in-game. This section about vector graphics is just to let you know it exists, what it is, and when to use it. The instructions given below are going to be more or less the same anyway, albeit with some minor changes that are specific to vector graphics.

# Preparations and Prerequisites

## Planning

<img src="https://media.tenor.com/hccwhstYLzgAAAAi/chara-dance-chara.gif">

*Source: [Ultama from Tenor](https://tenor.com/bMFIE.gif)*

### Do I have a design to refer off of?
If so, make sure it includes details from the front, sides, and back. You don't want to find out your reference material doesn't show the back then be left guessing what to put in the sprites.

And if you're the one making that reference material, **include it**!

### What actions can this character do that will require a sprite?
To make your process simpler, let's assign each action to its own row. From there, you can keep adding sprites for your animation towards the right. For non-animated sprites, you can group them together into one row as well.

### How big does each sprite have to be?
This is addressed in Sizing, so we'll skip over this for now.

### Do these sprites need to be animated?
#### If yes, how long is the animation (in seconds or frames) and how smooth does it have to be?
This will determine how many sprites you'll need to make for each action. Some actions can get away with just 3-4 frames total. Others, particularly the long complex moves in fighting games, may need upwards of 20 frames per action or sometimes even more.

## Sizing
What size (resolution) should each **sprite** be? You should strike a balance between your intended art quality and the game's performance. The higher the resolution, and the more sprites there are on-screen, the laggier it will be.

> For PSI, character sprites are 512px tall in editing but exported to 128px tall. This is useful in many ways: [downscaling](https://pcpartsgeek.com/downscaling/#:~:text=downscaling%20is%20the%20process%20of%20reducing%20the%20resolution%20or%20size%20of%20an%20image%2C%20video%2C%20or%20any%20other%20form%20of%20digital%20content.) to half the resolution reduces the performance impact by about 16x while also marginally improving the image quality thanks to [supersampling](https://en.wikipedia.org/wiki/Supersampling#:~:text=this%20is%20achieved%20by%20rendering%20the%20image%20at%20a%20much%20higher%20resolution%20than%20the%20one%20being%20displayed%2C%20then%20shrinking%20it%20to%20the%20desired%20size%2C%20using%20the%20extra%20pixels%20for%20calculation.%20the%20result%20is%20a%20downsampled%20image%20with%20smoother%20transitions%20from%20one%20line%20of%20pixels%20to%20another%20along%20the%20edges%20of%20objects.).
> 
> In PUB, and for pixel art in general, having jagged edges (a form of [aliasing](https://en.wikipedia.org/wiki/Supersampling#:~:text=Aliasing%20occurs%20because,horizontal%20or%20vertical.)) is actually crucial part of the pixel art aesthetic. This means that supersampling (a form of [anti-aliasing](https://cloudinary.com/glossary/image-aliasing#:~:text=causes%20aliasing%20issues.-,anti-aliasing%20algorithms,-.%20Implement%20algorithms%20that)) is actually harmful to the design and has no performance benefits, not to mention that all it does is create more work for the artists.

There are different approaches when it comes to making sprite sheets. The most common one is to make a reasonably large canvas, make your character sprites in the size you intended, then shrink the canvas once you're done! If you need more space, you can always just expand the canvas later.

We'll talk more in detail later about sprite-sheet-making basics. For now, we need to know how to properly size and space our sprites.

### Equal-size cells
The image below shows a sprite sheet where each individual sprite has the same size. This means that the character has to be centered properly in each cell so that it'll look just as centered when in-game. If done poorly, the character could look offset.

This approach takes advantage of the blank space to keep a consistent size, letting the artist determine how the character will be centered. As a downside, that blank space still takes up memory and may affect performance, particularly for large resolutions.

<img src="https://mir-s3-cdn-cf.behance.net/project_modules/disp/a83c07120129749.60abda77d6af9.png" width=65%>

*Source: [Mario Maiale from Behance](https://www.behance.net/gallery/120129749/Sprite-Sheet)*

> **💡 Tip:** When making equal-size cells, leave enough space for movement! As you can see on the image below, the character takes up more width when running sideways. It's easier to shrink the space taken up by each sprite, than it is to expand after the fact.
> 
> <img src="https://discuss.pencil2d.org/uploads/default/original/1X/8981294f2405202c498917a7c1594ead23dbfca4.png" width=65%>
>
> *Source: [Google...? from Pinterest](https://www.pinterest.com/pin/545639311086557164/)*

### Variable-size cells
Variable-size cells, on the other hand, shrink the character sprites down to the bare minimum size, cutting out as much unnecessary blank space as possible.

When making sprite sheets that don't have equally-sized cells, the sprites only need a minimum of 1 pixel gap between one sprite and another (although still not recommended). As you can see on the image below, certain sprite groups (like walking) are narrower than others (like punching).

Here, the engine (and therefore, the developers) determines how the character will be centered. This isn't normally a problem, but some sprites might be best centered with an offset (usually for running animations) which adds more work for the developers.

<img src="https://banner2.cleanpng.com/20180720/lci/d5746bb5b9acb0bfc8733acc2d780111.webp" width=65%>

*Source: [duplan from CleanPNG](https://www.cleanpng.com/png-pixel-art-digital-art-sprite-isometric-projection-5674954/)*

Well, of course, you can just ignore all of this and place your characters wherever you want as long as it's on the same sprite sheet and they all maintain the same relative size. Your developers will want to strangle you though.