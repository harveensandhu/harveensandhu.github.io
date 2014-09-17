---
layout: post
title: Responsive Images
---

##Why Do We Need Responsive Images?

When viewing a website that containes images, sometimes it can be hard to fully see what the image is, depending on the device you are using.
For example, if I were to view a website on a phone that contained images, in most cases I would have to zoom in to see the image. Some of the 
problems that we face as designers when it comes to images, is, the size, the quality and the overall user experience for the consumer. 
There is a need for responsive images, such as making it easier for the user to view the content, allowing the image to load quicker and also storage size and data use of the file.

Using responsive images can be hard due to determining the width, height, and viewport size of many devices that can be used. Such as, making sure that
if a user is on a phone the image renders perfect to the dimensions. Also, what can cause an issue is whether browsers support the code
that is being used. Using media queries at signficant breakpoints can allow different images to render at specific sizes, however just as using 100% on widths, 
this is not efficient in terms of size and supportability on a variety of devices.

###Below are examples of how to implement responsive images onto a web page:

#####CSS:
{% highlight css %}
 @media (min-width: 768px) {

        .image1{
          background-image: url('tablet-size.jpg');
          height: 400px;
          }
   
        }
        
        
  @media (min-width: 1024px) {

        .image1{
          background-image: url('desktop-size.jpg');
          height: 600px;
          
        }      
{% endhighlight css %}
Here using CSS, you can establish media queries simply to change the image at different breakpoints that will sit inside the desired container. (Note: if a desired with 
is established in previous CSS code of that class, the image will sit in the contraints given and in relation to the min-widths established)

####Picturefill:

In the head of the document:
{% highlight html %}

<script type="text/javascript">

//tell browser about picture element
  document.createElement('picture');
  </script>

  <script src="picturefill.js" async></script>
{% endhighlight html %}
In the html code:
{% highlight html %}
 <picture>
    <source media="(min-width:1024px)" srcset="image-desktop.jpg, image-desktop@2x.jpg">
    <source media="(min-width:768px)" srcset="image-tablet.jpg, image-tablet@2x.jpg">
      <img srcset="image-mobile.jpg, image-mobile@2x.jpg" alt="This is an image">
    </picture> 
{% endhighlight html %}
Here is an example using the picture tag, which allows you to state a media query, establish a range of images, including those for 
higher definition display, so that at each breakpoint, an image will load. This method seems quicker in terms of coding and one that could solve issues such as rendering and size limit.
