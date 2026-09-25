---
title: How to Make a Website Mobile Friendly
url: how-to-make-a-website-mobile-friendly
description: Google uses mobile-first indexing to rank websites. Learn how to build a responsive, mobile-first website with breakpoints, min-width media queries, containers, and Flexbox, and how to make sure Google can index your mobile content.
author: Cristian Marinescu
authorImage: /assets/images/blog/profilex.webp
date: 2026-09-25T09:00:00.000Z
tags:
    - post
image: /assets/images/blog/how-to-make-a-website-mobile-friendly.jpg
alt: Illustration of a responsive website on phone, tablet, and desktop screens
imageAlt: Illustration of a responsive website on phone, tablet, and desktop screens
---

Mobile traffic now accounts for roughly 60% of all internet usage, and Google uses mobile-first indexing to rank websites. According to [Google's official mobile-first indexing documentation](https://developers.google.com/search/docs/crawling-indexing/mobile/mobile-sites-mobile-first-indexing), the search engine uses the mobile version of your content for indexing and ranking. If your site isn't built for mobile devices first, you're losing visitors and search rankings. This guide walks you through building a fully responsive, mobile-first website from scratch, including practical code examples.

## Why Mobile First Matters

Google has made it clear that responsive websites rank better because of improved load times and usability. A website that loads fast and looks good on all mobile screens has a significant advantage over one that isn't built responsively.

Mobile-first programming means you build your HTML and CSS with mobile screens in mind first, then scale up to tablet and desktop. This approach isn't just a best practice, it actually makes development easier because it's simpler to make things grow into their containers than to squeeze desktop designs down into tiny screens.

## Common Breakpoints

These are the standard breakpoints to work with:

| Breakpoint | Target Device |
| --- | --- |
| 400px | Large Phones |
| 568px | Landscape Mobile |
| 768px | Tablet |
| 1024px | Small Desktop (Laptops) |
| 1300px | Normal Desktop |

When writing media queries, always use `min-width`. This means all styling from previous media queries carries over to the next step up, and only new CSS gets loaded on top. You never have to repeat code or redo sections, they just keep building toward the desktop version.

## Structuring Your CSS for Mobile First

Start your CSS file with mobile code at the top, then add media queries for bigger screen sizes as you go down the page. Begin by writing CSS to fit 320px screens, then add a media query for 400px `min-width` and make size adjustments for larger phones where needed.

This is the beauty of mobile first: instead of starting at desktop size and squeezing everything down, you start small and add to it step by step. Every step up brings you closer to the desktop version, and by the time you get there, all the heavy lifting was already loaded in from mobile.

## HTML Structure: Semantic Sections and Containers

Use semantic HTML and break your design into sections. Each section lives in its own `<section>` tag with a `.container` div inside, then content inside that:

```html
<section id="section-id">
    <div class="container">
        <p>Place content here</p>
    </div>
</section>
```

```css
.container {
    width: 100%;
    margin: auto;
    padding: 0 10px;
    max-width: 450px;
}
```

Why this works:

- `width: 100%` - makes containers grow with the screen size
- `margin: auto` - automatically centers the container horizontally
- `padding: 0 10px` - creates a buffer between content and screen edges
- `max-width: 450px` - stops growth at a point slightly larger than the biggest phone screen

The padding adds space INSIDE an element, while margin adds space around it. You want your container to be 100% width edge-to-edge, but you don't want your content touching the edges, padding creates that bumper.

For truly responsive design, set your container `max-width` to 1000px (perfect for the 1024px breakpoint), then change it at higher breakpoints as needed. There's no "one width to rule them all", it's entirely dependent on your design.

## Planning Your HTML for Mobile First

When given a desktop design, analyze each section individually and break it down into containers and pieces. Keep in mind how elements stack based on their order in the code:

```html
<div id="top">
    <div class="container">Code stuff</div>
</div>
<div id="middle">
    <div class="container">Code stuff</div>
</div>
<div id="right">
    <div class="container">Code stuff</div>
</div>
```

Top-to-bottom in HTML eventually becomes left-to-right on desktop when there's enough space.

## Desktop CSS with Flexbox

When you reach desktop size, use Flexbox to arrange the cards horizontally:

```css
.wrapper {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
}
```

Flexbox and CSS Grid are fundamental tools for responsive websites. With just a few lines of code, you can completely rearrange element placement.

## Ensuring Google Can Index Your Mobile Content

According to [Google's mobile-first indexing guidelines](https://developers.google.com/search/docs/crawling-indexing/mobile/mobile-sites-mobile-first-indexing), there are several critical factors to ensure your mobile site performs well in search:

### Keep Content Consistent Across Versions

Even consistent content can lead to different interpretations if the DOM or layout differs between desktop and mobile. Make sure your mobile site contains the same content as your desktop version. If your mobile site has less content, consider updating it so the main content matches the desktop version. You can use different designs for mobile to maximize user experience, just ensure the content is equivalent, because all indexing comes from your mobile site.

### Use the Same Meta Tags on Both Versions

Ensure your mobile and desktop sites use equivalent title elements and meta descriptions. Also, use the same robots meta tags on both versions. If you use different robots meta tags on your mobile site, especially noindex or nofollow, Google may not be able to crawl and index your pages when mobile-first indexing is enabled.

### Don't Rely on User Interaction for Critical Content

Google won't load content that requires user interaction (like swiping, clicking, or typing) to load. Make sure Google can see lazy-loaded content. This is especially important for mobile designs that use accordions or tabs, the content inside them needs to be accessible without interaction.

### Allow Google to Crawl Your Resources

Some resources on your mobile site may have different URLs than on your desktop site. If you want Google to crawl those URLs, make sure you're not blocking them with disallow rules.

### Check Your Structured Data

If you have structured data on your site, ensure both versions include it. The mobile site should have the same structured data as the desktop version, with correct URLs. This is particularly important for Breadcrumb, Product, and VideoObject structured data.

### Optimize Your Images for Mobile

Ensure images on your mobile site follow image best practices. Google specifically recommends:

- Provide high-quality images, don't use undersized or low-resolution images on mobile
- Use supported image formats and markup
- Don't use image URLs that change on every page load
- Use the same descriptive alt text on mobile as on desktop
- Ensure mobile page content quality matches desktop quality, use the same captions, filenames, and text

### Check Video Implementation

For videos on mobile:

- Don't use video URLs that change on every page load
- Use supported video formats in supported markup (`<video>`, `<embed>`, or `<object>`)
- Use the same video structured data on both versions
- Place videos where they're easy to find on mobile, if users have to scroll several times to find a video, its ranking may be negatively affected

## Conclusion

Building a mobile-friendly website comes down to a few core principles: start small at 320px, use `min-width` media queries, keep content consistent across devices, and optimize your images and metadata for search. These steps will improve your rankings and user experience.

If you'd rather skip the technical work, [Websitero](https://www.websitero.com/createyourwebsite) can build a responsive, mobile-first site for you, so you can focus on running your business.
