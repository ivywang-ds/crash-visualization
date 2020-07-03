# 1.1 Basic Concepts

##  Orientied Object and Pyplot 

Matplotlib graphs your data on [`Figure`](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure)s \(i.e., windows, Jupyter widgets, etc.\), each of which can contain one or more [`Axes`](https://matplotlib.org/api/axes_api.html#matplotlib.axes.Axes) \(i.e., an area where points can be specified in terms of x-y coordinates. It's called **object-oriented.**  In other words, ****you need to create objects.

```text
fig, ax = plt.subplots()  # Create a figure containing a single axes.
ax.plot([1,2,3,4],[3,2,3,4]) # plot some  data on the axes
```

![Output 1](../../.gitbook/assets/download%20%282%29.png)

{% hint style="warning" %}
According to last chapter,   could you find the flaw of the chart?
{% endhint %}

 There is a corresponding function in the [`matplotlib.pyplot`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.html#module-matplotlib.pyplot) module that performs that plot on the "current" axes, creating that axes \(and its parent figure\) if they don't exist. So the previous example can be written more shortly as

```text
plt.plot([1,2,3,4],[3,2,3,4])  # pyplot way
```

As noted above, there are essentially two ways to use Matplotlib:

* Explicitly create figures and axes, and call methods on them \(the "object-oriented \(OO\) style"\).
* Rely on pyplot to automatically create and manage the figures and axes, and use pyplot functions for plotting.

{% hint style="info" %}
If you forget the elements of plot, find it ****[**here**](https://app.gitbook.com/@ivy-wang/s/crash-visulisation/~/drafts/-MBLFg0lOJc2yNX6jGoq/visualisation-in-python/matplotlib#parts-of-figure)
{% endhint %}



