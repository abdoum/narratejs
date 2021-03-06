#Narrate.js

##About
Narrate.js is a javascript tool to add audio narration and synchronized page behavior to a web page. Narrate.js uses specific timings, provided by the web page author, to move around the page (e.g. scroll or jump), proceed through a slideshow, or execute an arbitrary code

##Usage
There are two ways to use narrate.js. The first way uses your HTML markup to setup the narration behavior. The second way uses javascript to set your up configuration. Either method requires you to first include the narrate.js file:

```html
<script src="path/to/javascript/folder/narrate.js"></script>
```

### Basic usage:
You should only use this method if you are either uncomfortable working in javascript, or you are prohibited from doing so. Narrate.js will work fine with this usage method, but it is generally a best practice to keep your markup (HTML) and your behavior (JavaScript) separated.

#### Steps:
1. Add an audio element with the appropriate audio source files. **Note: Not all browsers can play MP3 files so you should provide alertnatives, such as OGG and WAV, if you anticipate that your users will be using something other than Chrome or Safari. For a complete list of audio support in browsers (read this)[https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats#Browser_compatibility].**
2. Give the audio element a class that begins with "narrate-".
3. After the dash in "narrate-" add any name you would like so that the full class name on the audio file looks like "narrate-myname" or "narrate-mystory". The name after the dash is the class name that you give to all your elements you want included in the narration.
4. If you want to add any option flags to
5. Apply your chosen class name to all the elements you want included in the narration.



#### Options:


#### Sample Code:
```html
<audio autoplay class="narrate-mystory">
    <source src="narration.ogg" type="audio/ogg">
    <source src="narration.mp3" type="audio/mp3">
</audio>

<p class="mystory" data-start="0">Once upon a time...</p>
<img src="link/to/image.jpg" class="mystory" data-start="20000"/>
<p class="mystory" data-start="30000">...and they lived happily ever after.</p>
```


### Advanced usage:
This is the recommended method of using Narrate.js, because it offers the most flexibility and takes advantage of the full set of Narrate.js features. All

#### Steps:
1. Either include an audio element in your page or get the path to be referenced when setting up your narrate configuration.
2. Add all the elements to your page that you would like narrated. Give them all the same class name such as "mystory" or "myclass".
3.

#### Sample Code:
```html
<p class="mystory">Once upon a time...</p>
<img src="link/to/image.jpg" class="mystory"/>
<p class="mystory">...and they lived happily ever after.</p>
```

```javascript
narrate('mystory').config({
    audio:['path/to/audio.ogg','path/to/audio.mp3'],
    autoplay:true,
    control:'elemID',
    modulator:{
        preset:'robot',
        low:20,
        medium:30,
        high:40
    },
    timings:[0,20000,30000],
    prevEvent:{'elemID':'click'},
    nextEvent:{'elemID':'click'}
    crossfade:true,
    debug:true
});
```

## Troubleshooting
1. **Two or more narrations playing at the same time.**
    You may have set up your multiple narrations with autoplay set to true. Try configuring your narrations with only one or none of the autoplay set to true.

## Contact the author
If you have an issue with narrate.js (i.e. you think you discovered a bug or a feature request) please file an issue in GitHub. This is by far the easiest way to keep track of these kinds of things. If you still feel that a GitHub issue is not applicable to your problem the author can be reached through his personal website http://taylorhutchison.com



