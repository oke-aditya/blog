---
title: "Challenges with Machine Learning Projects"
toc: true
tag:
  - Projects
  - Machine Learning

excerpt: "Why Machine Learning Projects become code spaghetti?"
header:
  overlay_color: "#333"

---

## Introduction

Machine Learning Projects are hard to make. Maintaining them is even much harder.
Code becomes complex and end of month or year, it becomes impossible to understand it.

## But Why do projects become spaghetti code ?

### Lack of project structure

Projects that lack structure intially later become a mess. Usually this occurs when all code is dumped into a `src` folder.
This folder gets highly polluted and later it becomes hard to understand the codebease.
It is wiser to divide codebase into folders and sub folders, which make it easier to understand code.

### Not documenting the code or work 

Code that looks obvious right now becomes very hard to understand later.
Remember that code written should be re-usable and accessible to all people.
Easy methods such as type hinting, Docstrings are sufficient and do make code clear.

E.g. We write a function that takes a tuple denoting rectangle in `(x, y, w, h)` format.

{% highlight python %}
def foo(l):
  r = l[2] * l[3]
  return r
{% endhighlight %}

The above code is ok, but if I hadn't written what it does, it would be hard to understand.
Let's make this function better

{% highlight python %}
def area_rect(rect: Tuple):
  """
  Arguments:
    rect (Typle): A tuple denoting rectangle in (x, y, w, h) format.
    Where x, y are cordinates and w, h are width and height.
  Return:
    Area of rectangle.
  """
  area = rect[2] * rect[3]
  return area
{% endhighlight %}

How simple yet so powerful can docuemnting be !

### Missing requirements, not specifing how to use the project 

These are small additions, such as having a `requirements.txt` file can help people to replicate your computer packages.
Which would enable them to stay consistent with your work.

Having a proper `Readme` which describes how the projects is structured and how it should be run is really helpful.
It helps people to replicate your code and try it for their work.

### Not using functions

Most people work without writing functions. This does not make code modular and harder to comprehend.
Simply having functions with docstrings and calling them keeps content clear and easier to understand.
Writing functions on top of file and calling in `main` is easier. E.g. let's call the above area function.

{% highlight python %}

if __name__ == "__main__":
  rect = [0, 0, 10, 20];
  res = area_rect(rect)

{% endhighlight %}

### Over Engineering

Well all the above examples are use cases of under engineering or not following simple practices.
But at cases, people try to do too much and re-invent the wheel. There are multiple well supported and documented libraries available.
Try to use those and their methods, most functions are already present and work really well.

That's all for this blog! Hopefully your next project doesn't become a spaghetti code!
