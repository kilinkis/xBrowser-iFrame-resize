# xBrowser-iFrame-resize
How to Scale iFrame Content in IE, Chrome, Firefox, and Safari

source and all credits: https://collaboration133.com/how-to-scale-iframe-content-in-ie-chrome-firefox-and-safari/2717/

Scaling (or zooming) the content of an iFrame can be useful when you are trying to display an object in an area that does not match its original size. The below code scales an iFrame that is 1000 pixels wide down to 710px.

The values for the original dimensions are input after the #scaled-frame id selector and the scaled values are input after the #wrapper id selector. Just multiply the original dimensions by the zoom ration you want to use. For example, if you want to scale to 71% as shown in the example below, 1000px x 2000px becomes 710px x 1420px.

The zoom factor is input for the zoom, -moz-transform, -o-transform, and -webkit-transform properties.

Unless the @media screen and (-webkit-min-device-pixel-ratio:0) is defined, the iFrame will be scaled twice in Google. Leave this value set to 1.

To use the below code, simply copy and paste it into your html and update src="http://your-url.com/" to whatever content you’d like to display.

<style>
#wrapper { width: 710px; height: 1420px; padding: 0; overflow: hidden; }
#scaled-frame { width: 1000px; height: 2000px; border: 0px; }
#scaled-frame {
    zoom: 0.71;
    -moz-transform: scale(0.71);
    -moz-transform-origin: 0 0;
    -o-transform: scale(0.71);
    -o-transform-origin: 0 0;
    -webkit-transform: scale(0.71);
    -webkit-transform-origin: 0 0;
}

@media screen and (-webkit-min-device-pixel-ratio:0) {
 #scaled-frame  { zoom: 1;  }
}
</style>

<div id="wrapper"><iframe id="scaled-frame" src="http://your-url.com/"></iframe></div>
