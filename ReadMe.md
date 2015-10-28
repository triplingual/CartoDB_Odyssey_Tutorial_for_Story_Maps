# Using Odyssey.js for Making Story Maps

Contact me at [trip.kirkpatrick@yale.edu](mailto:trip.kirkpatrick@yale.edu)

This tutorial has been written so that it is generic enough for anyone to easily create a story map using an open geocoding interface and Odyssey.js. The tutorial is written specifically to support a course at Yale University, and is forked from a wonderful [@mapninja tutorial](https://github.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps) that works with CartoDB and whose pictures I haven't completely replaced yet. My context makes using CartoDB a little overkill, but I like that I can direct students to [@mapninja](http://github.com/mapninja)'s work if they want to go that direction. I like the [FOSS4G](https://2015.foss4g-na.org/) ethos and try to live it.

Just to be different from @mapninja and because I can't hang with his tattooing knowledge depth, I'm going with bowling lanes that are duckpins or offer duckpins. I also like bowling duckpins. Knowledge of lanes locations comes from [an amateur source](http://www.duckpins.com/houses.htm) (in the sense of people who love the sport), but I have no reason to doubt it. However, I'll still disclaim any pretense to accuracy in the map.

### In This Tutorial, You Will Learn To:

* **'Geocode'** your records so you'll have what to make them show up on the map
* Use the Odyssey.js 'Sandbox' to create a basic Story Map
* Use an historic map from DavidRumsey.com as a basemap in your Story Map
* Share your Odyssey.js Story Map with a URL, Embed Code, or host it yourself.

### What You Will Need Before Getting Started
* Something interesting to make a Story Map of!
* Information about the locations that make up your story
 * The **Latitude & Longitude** of your locations
 * Links (URLs) to images
 * Links (URLs) to more content
 * Narrative text about your subject
 * etc...

### Geocoding

Above, it's noted that you need to have the latitude and longitude of your locations. How do you get that?
* When I have fewer than, say, 20 street addresses to geocode, I prefer FOSS and/or educational institution options, like the open [Texas A&M geocoding service](https://geoservices.tamu.edu/Services/Geocode/Interactive/)
* You can also go to [Google Maps](http://maps.google.com), find your location, **right-click** on it and select **What's Here**. You can *cut-&-paste** the coordinates from the resulting info window)
![what's here](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/googlemapswhatshere.png)![Google Maps Coordinates](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/googlemapslatlong.png)
* If you code, the options open up significantly wider, but that's out of scope for this tutorial.


### It Could Be Helpful if You . . .
* Learn more about [Markdown](http://daringfireball.net/projects/markdown/), which is the text /ing markup syntax you will use to create the content in your Odyssey.js Story Map (It's also what this tutorial is written in!).
* Take a look at these pages from w3schools.com:
 * [HTML IMG element](http://www.w3schools.com/tags/tag_img.asp) — We'll use this to turn our image URL into the image in our pop-ups
 * [HTML A element](http://www.w3schools.com/tags/tag_a.asp) — We'll use this to turn our Link URLs into actual links in our pop-ups

## Creating a Story Map with Odyssey.js

Now that you've created the data for your Story Map, you're ready to go and build the narrative/navigation part of your application. We're going to use Odyssey.js for this. [Odyssey.js](https://github.com/CartoDB/odyssey.js) is actually a JavaScript library that you can use on your own web  server, but CartoDB has implemented a **Sandbox** that allows non-programmers to deploy a story map with very little coding and without any web server infrastructure at all. Odyssey.js uses a very simple text markup language called **Markdown**. This entire tutorial is actually written in **Markdown**, which allows GitHub to render the lists, HTML links, and other elements.

### Choosing an Odyssey.js Template

* First, go to [the Odyssey.js Sandbox](http://cartodb.github.io/odyssey.js/) and click on the **Create Story** button

![Create a Story](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/createstory.png)

* Now, **select** the **Slides Template**

![Slides Template](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/slidestemplate.png)

You should now see the **Odyssey.js Sandbox** template for a slideshow style story map. Note that you will be editing in the panel labeled **Odyssey Sandbox** and your edits will change the look of the content panel on the left, as well as the map. The **Odyssey Sandbox** panel will not be visible in the final story map.

![Odyssey.js Slide Template Sandbox](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/odysseyslidestemplate.png)

### Customize the **config block** of Your Odyssey.js Applicaiton

* At the top of the *Oddysey Sandbox** panel, you should see two lines of text that look like this:
```
	```
	-title: "Odyssey example FTW"
	-author: "CartoDB"
	```
```

* Go ahead and customize it so that it reflects the **title** and **author** for your project:
```
    ```
    -title: "Duckpins Across Connecticut"
    -author: "Trip Kirkpatrick"
    ```
```

### Adding a Slide to Your Story Map

Now you're ready to start adding the content of your slides to the Oddysey.js Sandbox. Now is a good time to review a little bit about the Markdown language that drives the Odyssey.js application. As mentioned above, [Markdown](http://daringfireball.net/projects/markdown/syntax) is a text markup language that acts a bit like shorthand for writing HTML code. Markdown simplifies the process of creating HTML text formatting, add ing images, links and other content to a page meant for the web. This entire tutorial is written in [Markdown](http://daringfireball.net/projects/markdown/syntax).
Odyssey.js uses [Markdown](http://daringfireball.net/projects/markdown/syntax) in thhe way it is intended (to format text and content) with one important exception. The **H1 Heading** element is used by Odyssey.js to signal the beginning of a "new slide." You can see this in the **Odyssey.js Sandbox** if you count the number of **dots** at the top of the content panel on the left, and then count the number of lines in the ODYSSEY SANDBOX panel on the right that begin with the **\#** symbol. Same number! Each **H1 Header** line in the Sandobox define the begining of a new slide, as well as the Title text of that slide.

#### Here are a few more important bits of [Markdown](http://daringfireball.net/projects/markdown/syntax) syntax:
##### Headers

    # Level 1 (H1) Header, also indicates the beginning of a new slide in Odyssey.js
    ## Level 2 Header
    ### Level 3 Header
And will render like this:
# Level 1 (H1) Header, also indicates the beginning of a new slide in Odyssey.js
## Level 2 Header
### Level 3 Header

##### Paragraph Text
	Paragraph text is just paragraph text. You can **bold** text or use *italics*. Those are the most common uses and they end up looking like this:
Paragraph text is just paragraph text. You can **bold** text or use *italics*. Those are the most common uses and they end up looking like this.
##### Lists

    1. This
    2. Is
    3. An
    4. Ordered
    5. List

    * This
    * Is
    * A
    * Bullet
    * List
Which renders like this:  
1. This  
2. Is  
3. An  
4. Ordered  
5. List

* This
* Is
* A
* Bullet
* List


##### Links

    Create Links like this: [Google](http://google.com)

Which Renders like this: [Google](http://google.com)

##### Images
You can place an image like this:

	![Mustache Salovey](https://31.media.tumblr.com/a9fef6920600c4ce095d83cde0f7c185/tumblr_inline_mifn6hHBM31qz4rgp.jpg "Pre-presidential Salovey")

Which will render like this:

![Mustache Salovey](https://31.media.tumblr.com/a9fef6920600c4ce095d83cde0f7c185/tumblr_inline_mifn6hHBM31qz4rgp.jpg "Stachio")

That's as far as we are going to dive into Markdown for this tutorial, but there is loads more you can do with it. If you want to find out more, go to [http://daringfireball.net/projects/markdown/syntax](http://daringfireball.net/projects/markdown/syntax)

## Making Your First Odyssey.js Slide

Ok, time to create your first Story Map slide.
* Return to the **Odyssey Sandbox** and place your cursor on the blank line just above the deafult first slide **H1** header and add the **Title Text** you want for your first slide, like this:
```
    ```
    #Johnson's Lanes
    ```
```

* Hit **Enter**
* Add information for the latitude and longitude (that you got from Geocoding before) and zoom level (which will take a bit of fiddling)
```
    ```
    - center: [41.36849786, -72.91981278]
    - zoom: 9
    ```
```

![Add a New Slide](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/addslide.png)

### Add more slides!
Now that you know how, you can delete the **Sandbox** Markdown below your first slide and add all of the slides you want! Insert Images, etc. . . .

## Using a Georeferenced Map from [DavidRumsey.com](http://www.davidrumsey.com/view/georeferenced-maps) as Your Basemap

It's possible to change the basemap of your **Odyssey.js** Story Map, either using the Basemap Selector at the bottom of the **Sandbox** panel, or by adding a bit of code to the **config block**. This is a bit tricky, but I will briefly explain it here.

* First, go to [DavidRumsey.com](http://www.davidrumsey.com/view/georeferenced-maps) and find a map that is georeferenced that you can use (I won't go into the use of his georeferencer here, but you can search for any map you want and georeference it yourself). There is a **Map Finder** at the bottom of the page, which is currently the easiest way to locate a map for the area you want.
* Click on the dots to preview the maps, and once you find one, click on **View this map in... *Georeferencer***

![Rumsey Map Finder](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/rumseymapfinder.png)

* Click on the **Embed OGC WMTS tiles** link at the top right of the map window

![Embed OGC WMTS](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/embedtiles.png)

* Click on the **Affine Thumbnail**  

![Affine Thumbnail](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/affine.png)

* Find the *MapBox JS** Source code link on the right side of the page and click on it

![MapBox Embed Code](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/mapboxembedcode.png)

* OK, here's the tricky part. It looks scarier than it is. Find the first URL for the Tile Server in the code. It should be **Green**. Highlight & copy that URL, with the quotes. It will look something like this:  
```
	"http://georeferencer-0.tileserver.com//266b60e098fda1ddbe521ebff0e4d8676a549302/map/CGtnosESWB2NnsgVyjmQc5/201411301752-7AINSs/affine/{z}/{x}/{y}.png"
```
![Tile Server URL](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/tileserverurl.png)

* Return to your **Odyssey.js Sandbox** and add the following text to your **config block** at the top of your Markdown code, using the URL you copied from davidrumsey.com, like this:  

```
	-baseurl: "http://georeferencer-0.tileserver.com//266b60e098fda1ddbe521ebff0e4d8676a549302/map/CGtnosESWB2NnsgVyjmQc5/201411301752-7AINSs/affine/{z}/{x}/{y}.png"  
```

## Sharing your Story Map
Once you have created all the slides you are interested in putting into your Story Map, you are ready to share your work with the world. The **Odyssey.js Sandbox** allows you to do this in three ways:

#### Sharing with an URL or Embed code
**Odyssey.js** can export your Story Map directly to a site called [bl.ocks.org](http://bl.ocks.org), which is just a platform for sharing and rendering JavaSript code, or give you an **IFRAME** code snippet to paste into your blog, or other website.

* First, click on the **Share** button (it looks like a paper airplane)

![Share Story Map](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/sharestorymapbutton.png)

* Select whether you want to share an **URL** of Embed an **IFRAME** into an existing website, then click **Copy** to copy the **URL** or **Code** to your clipboard. For this tutorial, just select the **URL** option.

![Share Story Map](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/shareurl.png)

Here's the [bl.ocks.org](http://bl.ocks.org/anonymous/raw/bfbe91970e81ef2faa43) version **(URL)** of the tutorial map.


And in the [course blog](http://wgss380f2015.coursepress.yale.edu/2015/10/26/odyssey-js-map/).


#### Downloading and Hosting Your Story Map
You can also download the code for your Story Map and host it on your own Web Server (provided you have one).

* Click on the **Download story** button in the **Odyssey Sandbox** panel and save the resulting **.zip** file to your computer.
* Extract the **Odyssey.html** file and copy it to your Web Server. It's ready to go! You can make customizations to the code, if you like.

![Download Odyssey](https://raw.githubusercontent.com/mapninja/CartoDB_Odyssey_Tutorial_for_Story_Maps/master/images/edit/downloadodyssey.png)

Here's the map hosted on [a Yale web server](http://sprout002.sprout.yale.edu/docc/f15/mapping/odyssey.html) I use.

## Here is the Markdown Code for the Sample Story Map I Just Walked Through, Above:

  ```
	-title: "Duckpins Across Connecticut"
	-author: "Trip Kirkpatrick"
	-baseurl: "http://georeferencer-0.tileserver.com//b5bc704239bdb10e8d323f9ade18c0d65de168c6/map/J7HhAxvJEL29OwQw7N4jJZ/201412192146-E3UrAF/affine/{z}/{x}/{y}.png"
	```

	#Duckpins Across Connecticut
	##Where to get your bowl on
	```
	- center: [41.36849786, -72.91981278]
	- zoom: 9
	```

	Duckpin bowling takes place in [a very few parts of the USA](http://www.duckpins.com/houses.htm). Fortunately for anyone in Connecticut who wants to bowl this way, we have several options .


	#Johnson's Lanes
	##Hamden
	```
	- center: [41.36849786, -72.91981278]
	- zoom: 10
	L.marker([41.36849786, -72.91981278]).actions.addRemove(S.map)
	```

	This alley is 3.93 miles from my office at HGS.


	#Woodlawn Duckpin Bowling Center
	##West Haven
	```
	- center: [41.25957012, -72.96393912]
	- zoom: 10
	L.marker([41.25957012, -72.96393912]).actions.addRemove(S.map)
	```

	This alley is 4.05 miles from my office at HGS.


	#Highland Bowl Cheshire
	##Cheshire
	```
	- center: [41.53197533, -72.89479854]
	- zoom: 10
	L.marker([41.53197533, -72.89479854]).actions.addRemove(S.map)
	```

	This alley is 15.29 miles from my office at HGS.


	#Perillo's Bowl-A-Drome
	##Waterbury
	```
	- center: [41.55246416, -73.00245569]
	- zoom: 10
	L.marker([41.55246416, -73.00245569]).actions.addRemove(S.map)
	```

	This alley is 17.03 miles from my office at HGS.


	#St. Joseph's Lanes
	##Waterbury
	```
	- center: [41.54514542, -73.04669469]
	- zoom: 10
	L.marker([41.54514542, -73.04669469]).actions.addRemove(S.map)
	```

	This alley is 17.21 miles from my office at HGS.


	#T-Bowl Lanes
	##Newington
	```
	- center: [41.65569301, -72.72375509]
	- zoom: 10
	L.marker([41.65569301, -72.72375509]).actions.addRemove(S.map)
	```

	This alley is 26 miles from my office at HGS.


	#Danbury Lanes
	##Danbury
	```
	- center: [41.4192612, -73.45107284]
	- zoom: 10
	L.marker([41.4192612, -73.45107284]).actions.addRemove(S.map)
	```

	This alley is 28.05 miles from my office at HGS.


	#Highland Bowl Hartford
	##Hartford
	```
	- center: [41.76624689, -72.71160042]
	- zoom: 10
	L.marker([41.76624689, -72.71160042]).actions.addRemove(S.map)
	```

	This alley is 33.32 miles from my office at HGS.


	#K of C Lanes
	##Torrington
	```
	- center: [41.79695483, -73.12477256]
	- zoom: 10
	L.marker([41.79695483, -73.12477256]).actions.addRemove(S.map)
	```

	This alley is 34.98 miles from my office at HGS.


	#Arcade Lanes
	##Torrington
	```
	- center: [41.81182388, -73.12117084]
	- zoom: 10
	L.marker([41.81182388, -73.12117084]).actions.addRemove(S.map)
	```

	This alley is 35.91 miles from my office at HGS.


	#Holiday Lanes
	##Manchester
	```
	- center: [41.7677111, -72.56432808]
	- zoom: 10
	L.marker([41.7677111, -72.56432808]).actions.addRemove(S.map)
	```

	This alley is 36.68 miles from my office at HGS.


	#Laurel Bowling Lanes
	##Winsted
	```
	- center: [41.8689231, -72.96067763]
	- zoom: 10
	L.marker([41.8689231, -72.96067763]).actions.addRemove(S.map)
	```

	This alley is 38.49 miles from my office at HGS.


	#Family Bowl
	##Waterford
	```
	- center: [41.34209212, -72.12564027]
	- zoom: 10
	L.marker([41.34209212, -72.12564027]).actions.addRemove(S.map)
	```

	This alley is 41.71 miles from my office at HGS.


	#Lucky Strike Lanes
	##Mansfield
	```
	- center: [41.73775635, -72.25811745]
	- zoom: 10
	L.marker([41.73775635, -72.25811745]).actions.addRemove(S.map)
	```

	This alley is 45.46 miles from my office at HGS.


	#TKB Lanes
	## Rockville, members only
	```
	- center: [41.86537713, -72.45084037]
	- zoom: 10
	L.marker([41.86537713, -72.45084037]).actions.addRemove(S.map)
	```

	This alley is 45.49 miles from my office at HGS.
