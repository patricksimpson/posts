---
title: "The Basics of Media Queries"
date: "2012-05-12"
summary: "All about media queries"
tags: ["old", "programming"]
---

Media queries are an integral part of responsive web design and when used properly can be a vital resource for your design. Media queries allow you to determine the current “medium” or “media” that your webpage is currently displaying on. With this tool, it gives you the ability to be extremely flexible with what styles apply to what types of screens.


Media Queries 101

A very simple usage of media queries, which was allowed under HTML4.0.1 and CSS2, is the print/screen media. This was done as follows:


	<link rel="stylesheet" type="text/css" media="screen" href="normal-styles.css">
	<link rel="stylesheet" type="text/css" media="print" href="print-styles.css">

As you can see here, media=”screen” targets your typical browser while and media-=”print” targets the printer. With the print media selected, you can determine how your page appears when a user prints your webpage. These styles would not be applied otherwise.

Media Query Syntax

This is where things might start getting a little complex. Media queries use the CSS2.1 grammar rules, but keep in mind that these more complex media queries need modern browser, which can support CSS3. I will be keeping it simple in this post, but here are some basics to remember.

Media Types:

* all
* braille
* embossed
* handheld
* print
* projection
* screen
* speech
* tty
* tv

These will be used as your basic media type selector (user agent), which the most common are “screen” and “print”.

Media Query Keywords

These are some of the keywords used in media queries: only, and, not. The logical OR is expressed by a comma.

Remember to keep spacing between your keywords.

Up to this point you should be able to craft basic media queries. For example:

 <link rel="stylesheet" type="text/css" media="not screen" href="odd-styles.css">
applies to everything that is not a “screen” based media type.

Media Features:

These allow for selecting based on variable media features. Media features should be surrounded by a open parentheses ”(” and and closing parentheses ”)”. A complete list of each feature is as follows:

* width
	* min/max prefix supported.
	* width of viewport, including scrollbar.
* height
	* min/max prefix supported.
	* height of viewport, including scrollbar.
* device-width, device-height
	* min/max prefix supported.
	* width/height of the rendering surface.
* orientation
	* min/max prefix not supported.
	* only landscape and portrait are supported values.
* aspect-ratio
	* min/max prefix supported.
	* width viewport value to the height viewport value.
* device-aspect-ratio
	* min.max prefix supported.
	* width of the device to the height of the device.
* color
	* min/max prefix supported.
	* value is the number of bits per pixel supported, non-color devices will return 0.
* color-index
	* min/max prefix supported.
	* value is the number of bits supported in the devices color table, if not supported, it will return 0.
* monochrome
	* min/max prefix supported.
	* value is the bits per pixel, if the device is non monochrome, will return 0.
* resolution
	* min/max prefix supported.
	* min max must be used for non-square pixel devices.

Now you should be ready to start some serious media queries!

Examples

    <link rel="stylesheet" type="text/css" media="screen and (min-width: 330px)" href="330.css">

This stylesheet applies to screens, with a minimum width of 330px, everything smaller than 330px, these styles will be ignored.

     <link rel="stylesheet" type="text/css" media="only screen and (max-width: 960px)" href="960.css">

This stylesheet applies only to screens, with a maximum supported with of 960px. Everything larger than 960 pixels, these styles will be ignored.

     <link rel="stylesheet" type="text/css" media="screen and (max-device-width: 800px), (orientation: landscape)" href="800-land.css">

This will apply to any screen with the max width of 800 pixels and larger, or it will apply to screens that are landscape (such as a handheld device flipped into landscape mode).

The @ Rule

This can be used inside stylesheets to apply a “quick” media query. This is used by the following format: @media screen and (min-width: 330px) { … } where the “…” would be your styles to apply to that specific media query.

An example of this type of media query is as follows (in a normal style sheet):


    /* Styles Above */
    /*...*/
    @media only screen and (min-width: 35em) {

    .post{
        display: block;
        border: 1px solid #ddd;
        min-width: 23em;
    }

    }
    /* Styles Below Continue... */
    /*...*/

Wrapping Up

While there are a lot more examples I could go into, this should help you get started on learning media queries, and what they could be used for. If you have any queistions about media queries, feel free to contact me. Also, for more information, please my reference: W3C – Media Queries.

I hope this helps!

References:

 http://www.w3.org/TR/css3-mediaqueries/
http://www.findmebyip.com/litmus/
