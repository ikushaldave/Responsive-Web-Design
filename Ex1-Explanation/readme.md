## BLOCK-readText

## Responsive Web Design

These days it is hard to find someone who doesn't own a mobile connected to the internet. Everyone doesn't own a laptop or desktop but it's possible everyone owns a mobile device.

With the growth of mobile devices the internet users also growing like crazy. And therefore a new challenge came how to build websites suitable for all screen users. The users who are using a large monitor screen for them also as well as for the mobile users also.

In response to this "Responsive Web Design" came which helps in building a website which will be suitable for all screen size, no matter how large or small, mobile or desktop.

### What is Responsive Web Design?

Responsive web design is an approach to develop all screen-size versions of your websites. No matter which device your website is being opened, who is the users. All users owning a small device or larger device will get a better experience with responsive web design.

For example, check out the [AltCampus](https://boagworld.com/dev/semantic-code-what-why-how/) website in any device. You'll find the website is friendly in every device.

The responsive web design is accomplished by making the layouts `responsive` and `adaptive`.

> ##### Responsive Vs Adaptive
>
> Responsive layout that reacts quickly and positively to any change.
> The responsive layouts are also known as flexible layouts, which will have fluidity.
> It will continuously change based on different factors.
> If the viewport width changes, the layout will also change fluidly.
>
> While the adaptive layouts changes based on a new purpose or condition. In CSS "media queries" are used to conditionally apply CSS rules.
>
> The combination of both "responsive" and "adaptive" is ideal to create a functional responsive website.

The responsive web design is broken into three main components: `flexible layouts, media queries, and flexible media`.

#### Flexible Layouts

We have already discussed flexible layouts and how to create in the chapter [Positioning Content](https://github.com/AltCampus/AC-STYLE-positioning-content). That gives us a push towards creating a responsive website. We already know to create a flexible layout or responsive layout which will respond quickly and fluidly to any change.

Next thing we need to make our layout adaptive. Making flexible our layout alone is not enough. When browser viewport is too small(say on mobile) multi-column layouts may break. In fact, showing multi-column on small devices is not a good experience. Also, texts become illegible when the layout gets too small or large. This is where "media queries" comes in to make the layout adaptive for a better experience.

#### Media Queries

Media queries provide the ability to apply CSS rules conditionally. We can apply CSS specifically for an individual browser or depending on the viewport width or device orientations.

##### Initializing Media Query

There are a couple of different ways to use media queries. The most recommended is using `@media` rule inside an existing stylesheet.

```
  @media screen and (max-width: 992px) {
    .....
  }
```

Let's see how this media rule works practically.

For example:

```
  <!-- CSS -->
  body {
    background-color: red;
  }
  <!-- Media Queries -->
  @media screen and (max-width: 992px) {
    body {
      background-color: green;
    }
  }
  @media screen and (max-width: 768px) {
    body {
      background-color: blue;
    }
  }
```

In the above example, the `background-color` of the body will be `red` by default. But there are two other conditions also which are applied using media queries, those are the conditional CSS rules. When the viewport width will be below `992px` the `background-color` will be `green` and below `768px` it will be `blue`.

There are other ways also to apply media query, importing a new stylesheet using `@import` rule or by linking a separate stylesheet within the HTML document. No matter what you chose, but the most recommended is the `@media` rule that we have seen above.

_**HTML**_

```
  <!-- Separate CSS File -->
  <link href="styles.css" rel="stylesheet" media="all and (max-width: 1024px)">
```

_**CSS**_

```
  /* @import Rule */
  @import url(styles.css) all and (max-width: 1024px) {...}

```

The media queries provide the ability to present our same HTML content in different styles on different sizes of screens. It can be different for small devices and different for larger devices.

The media rule depends upon different factors like `media type, logical operators, and media features`. The query begins with `@media` follows by "media type" and may include "media features and values". When the condition for media feature and value is true the styles are applied or if it is false the styles are ignored.

##### Media Type

As mentioned the media query may include media types followed by other expressions. The common media types are `all`, `screen`, `print`, `tv`, and `braille`. If the media query does not include any media type, the query considers `screen` as a default media type.

##### Logical Operators in Media Queries

The media queries include three logical operators(`and, not, only`), which is combined to build powerful expressions.

_**and**_

The `and` operator is used to add an extra condition to the media query. For example:

```
  @media all and (min-width: 768px) and (max-width: 992px) {
    .....
  }
```

The above example includes two conditions, `min-width: 768px` and `max-width: 992px`. Thefore the expressions will be applied to all the media type between `768px` and `992px`.

_**not**_

The `not` logical operator negates a query specified in the media query. The media rule select all the query to accept the specified one. For example:

```
  @media not screen and (color) {
    .....
  }
```

In the above example, the expression will be applied to the screens which do not have color. The black and white or monochromatic screens would be selected here.

_**only**_

```
  @media only screen and (orientation: portrait) {
    ...
  }

```

The above example includes the `only` operator. The expressions will be applied only when the screen will be in portrait orientation.

##### Media Features in Media Queries

The media features play an important role in media queries. Because media features only decide what is going to be selected in the media query expressions. In the above examples of operators, you can see the `min-width`, `max-width`, `orientation` etc are the media features.

_**Height & Width Media Features**_

The most common media feature used in media query is `height` and `width`. Normally the height and width media feature is prefixed with `min` and `max`.

> ##### The Min and Max Prefixes
>
> The `min` prefix indicates the values greater than or equal to while `max` indicates the value less than or equal to.

```
  @media all and (min-width: 320px) and (max-width: 768px) {
    .....
  }
```

The `height` and `width` media features are based on the viewport width and height. When the expression meets the viewport's width or height specified in the media query the styles are applied.

While working on responsive web design the most common media feature you will use are the `min-width` and `max-width`. These features help in building a responsive website for desktop as well as mobile devices equally.

_**Orientation Media Features**_

The `orientation` media features include `landscape` and `portrait` values. Any of these values used in the expression determines whether the device is in `landscape` or `portrait` orientation.

```
  @media all and (orientation: landscape) {
    .....
  }
```

For example in the above expression when the display will be in `landscape` orientation then only the styles will be applied.

> ##### Landscape Vs Portrait
>
> The `landscape` mode is triggered when the display is wider than taller, and `portrait` mode triggered when the display is taller than the wider.

_**Aspect Media Features**_

The `aspect-ratio` and `device-aspect-ratio` features specifies the `width/height` pixel ratio of the device. If the device's ratio is equal to the ratio specified in the expression the styles will be applied.

```
  @media all and (min-device-aspect-ratio: 16/9) {...}
```

In the above example if the device's ratio will be equal to or greater than `16/9` the styles will be applied.

> The device ratio can be calculated by dividing the device's width in pixel by the height in pixel.

You can also prefix this feature with `min` or `max` stating the ratio below or above specified in the expression.

_**Resolution Media Features**_

The `resolution` media features specify the resolution of the device in pixel, also known as DPI or dot per inch.

```
  @media print and (min-resolution: 300dpi) {
    .....
  }
```

_**Other Media Features**_

Other media features like `color`, `color-index`, and `monochromatic` are also available. These media features are less common but can be used whenever needed.

All these media factors like `media type`, `logical operators`, and `media features`, you may not find useful for now. But each and everything that we have discussed above is helpful and can be used whenever needed.

The most common media type, logical operators, and media features you will using are `screen`, `and`, and `min-width & max-width` while developing a responsive website. But that doesn't mean others are not useful. Other factors are also useful depending upon the use cases.

Let's check out one demo over media query how the common factors are used to build a website responsive.

##### Media Queries Demo

In the above example, I have defined two media queries. One for the device below `768px` screen size and another for the device whose screen size is between `768px` and `992px`. And above the `992px` screen size the normal CSS is getting applied. The `768px`, `992px` in the media query is known as `breakpoints`.

If you look at the above code inside the media queries, these are the normal CSS rules. The only difference is that this CSS will be triggered only when the conditions will be true. So creating a responsive website is not a big deal. It's just you need to define a breakpoint where you want to restructure your content according to device screen size for a better experience.

##### CSS Breakpoints to Create Responsive Layout

CSS breakpoints are the points where the content responds according to the device width, allowing the best possible way to show the layout to the user. You have already seen in the above example how the structure of the layout is changing depending upon the two breakpoints.

The tricky part about the breakpoints is that how to chose one. Should we chose the breakpoint based on the device or based on the content.

Deciding breakpoint based on the device is a bad idea. And the beginner always thinks it's a good idea. There are already a lot of devices to worry about, and every day new devices are releasing. Therefore we should take such an approach that covers all the devices.

The ideal option is to choose breakpoints based on the content. This will allow you to simply add breakpoints where your content needs adjustment. This will keep your media query lot simpler and manageable.

Typical device breakpoints widely used:

_Extra small devices (phones, 600px and down)_

```
  @media screen and (max-width: 600px) {
    ...
  }
```

_Small devices (portrait tablets and large phones, 600px and up_

```
  @media screen and (min-width: 600px) and (max-width: 768px) {
    ...
  }
```

_Medium devices (landscape tablets, 768px and up)_

```
  @media screen and (min-width: 768px) and (max-width: 992px) {
    ...
  }
```

_Large devices (laptops/desktops, 992px and up)_

```
  @media only screen and (min-width: 992px) and (max-width: 1200px) {
    ...
  }
```

_Extra large devices (large laptops and desktops, 1200px and up)_

```
  @media only screen and (min-width: 1200px) {
    ...
  }
```

These are the five common groups that cover all the devices.

Always try to define a breakpoint where your content breaks and needs to be restructured. It should be always based on your content, not devices.

#### Mobile First Approach

When building a responsive website, for writing media query we can two approaches: `mobile-first approach` and `desktop-first approach`. The above examples are based on the `desktop-first` approach.

In a `mobile-first` approach the styles are applied first to the mobile-devices or small devices. Thereafter the advanced styles are written to override the styles for larger screens using a media query. This approach is taken using `min-width` media features. For example:

```
  /* This applies from 0px to 600px */
  body {
    background: red;
  }

  /* This applies from 600px onwards */
  @media (min-width: 600px) {
    body {
      background: green;
    }
  }
```

According to the above example, the body will have a `red` background below `600px`. But it's background will change to green at `600px` and beyond.

> ##### Desktop First Approach
>
> On the other hand in `desktop-firs`t approach the styles are first applied to desktop or larger devices.
> Thereafter advanced styles are written to override the styles for small screen devices via media query.
>
> ```
>   body {
>     background: green;
>   }
>
>   /* This applies from 0px to 600px onwards */
>   @media (min-width: 600px) {
>     body {
>       background: red;
>     }
>   }
> ```
>
> The body will have `green` background for all width devices, but if the screen is below `600px` the beckground will change to red.

It is believed that taking a `mobile-first` approach is considered as best practice, and it's true also. Although you can take any approach that depends upon personal choice. But the `mobile-first` approach has some advantages over the `desktop-first` approach.

Generally, the layout for larger devices is a bit complicated than the smaller devices. And loading desktop styles on smaller viewport devices would be a bad idea. Most of the time default we can rely on default properties of elements for smaller screens.

_**Typical Breakpoints of Mobile-First Appraoch**_

```
  @media screen and (max-width: 600px)  {...}
  @media screen and (min-width: 600px)  {...}
  @media screen and (min-width: 768px)  {...}
  @media screen and (min-width: 992px) {...}
  @media screen and (min-width: 1200px) {...}

```

##### Mobile First Demo

#### Viewport

The viewport is a visible area of the window in which web content can be seen. Often the viewport size varies from device to device. The mobile devices have smaller viewport and larger for desktops or larger devices.

Earlier the websites were only used to design and develop for computer screens. Then we started surfing websites on mobile devices or smaller screen devices. The website designed for the computer screen was fixed and large to fit on the smaller viewport.

To fix the issue "responsive web design" introduced. Nowadays mobile devices are pretty good to display websites with responsive web design and a little bit of assistance.

Apple invented the `viewport` meta tag to let control over the viewport size, scale, and resolution of a website.

```
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

The viewport meta tag is applied inside the `head` tag in the HTML document. That gives instruction to the browser to control the page's dimension and scaling.

**Viewport Width & Height**

The `width=device-width` part will inherit the default width of the device for the best results and best view. Apart from viewport width you can also viewport height, `height=device-height`.

**Viewport Scale**

The `initial-scale` of the website should be set to `1` that sets the zoom level when page load for the first time. The `initial-scale` can be set between `0` to `10`.

Apart from `initial-scale` to control scalable capability of the page there comes few other properties also, `minimum-scale`, `maximum-scale`, and `user-scalable`.

The `minimum-scale`, and `maximum-scale` values will determine how smaller or larger the viewport of the device will be scaled. The `minimum-scale` value must be lower than or equal the `initial-scale` value. Similarly, the `maximum-scale` value must be equal to or greater than the `initial-scale` value.

By default, the `user-scalable` value is `yes`. However, if you want to turn off the zooming you can set the value to `no`. Turning off the zooming ability is not a good idea. It harms the accessibility, usability, prevents disable people from viewing the website as they desire.

Never forget to apply this `viewport` meta tag in your document.

Here is an example of a webpage with and without a `viewport` meta tag.

#### Flexible Media

When working with responsive web design apart from the container and flexible layout, the media - images, video players, audio players also demand a bit of attention. The texts can be resized and will flow nicely to fill the container. That's not too hard. The images, videos, audio, and other media types need to be scalable as the viewport size changes.

One way to fix the issues applies to `max-width: 100%` to these media types. Applying so when the viewport size gets smaller the media will also scale down as per the container width.

```
  img, video, audio {
    max-width: 100%;
    height: auto;
  }
```

##### Flexible Embeded Media

Unfortunately, the `max-width: 100%` trick doesn't work well with the embedded media, specifically `iframes`. For example, when we embed third-party media such as YouTube, it requires an `iframe` tag.

To make embedded media fully responsive, wrap the embedded media inside a parent and position it absolutely. The parent must have width `100%` so that it can resize according to the viewport size. The height of the parent will be `0`.

The `padding-bottom` is applied to the parent which will be the same as the aspect ratio of the video. This will keep the parent's height proportional to the width. For example, if the aspect ratio of the video is `16:9`, then the `padding-bottom` would be calculated in percentage, `(9/16)*100`. That brings the value `56.25%`.

**Flexible Embedded Media Demo**

```
  <!-- HTML -->
  <div class="wrapper">
    <iframe width="560" height="315" src="https://www.youtube.com/embed/LXb3EKWsInQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
  </div>

  <!-- CSS -->
  .wrapper {
    height: 0;
    padding-bottom: 56.25%; /* 16:9 */
    position: relative;
    width: 100%;
  }
  iframe {
    height: 100%;
    left: 0;
    position: absolute;
    top: 0;
    width: 100%;
  }
```
