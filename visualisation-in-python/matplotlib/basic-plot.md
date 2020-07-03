# Basic Plot

##  Orientied Object and Pyplot 

Matplotlib graphs your data on [`Figure`](https://matplotlib.org/api/_as_gen/matplotlib.figure.Figure.html#matplotlib.figure.Figure)s \(i.e., windows, Jupyter widgets, etc.\), each of which can contain one or more [`Axes`](https://matplotlib.org/api/axes_api.html#matplotlib.axes.Axes) \(i.e., an area where points can be specified in terms of x-y coordinates. It's called **object-oriented.**  In other words, ****you need to create objects.

```text
fig, ax = plt.subplots()  # Create a figure containing a single axes.
ax.plot([1,2,3,4],[3,2,3,4]) # plot some  data on the axes
```

![Output 1](../../.gitbook/assets/download%20%281%29.png)

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

## Sample Plot

### Lineplot

{% hint style="info" %}
**What to learn:**

*  **Add multiple lines on one figure**
* **Set  xlabel name and ylabel**  
* **Set  title name**
* **Set and show legend**
{% endhint %}

```text
x = np.linspace(0, 3, 100)
plt.plot(x, x, label='linear')       # Plot  'linear line' on axes.
plt.plot(x, x**2, label='quadratic') # plot 'quadratic line' on the same axes
plt.plot(x, x**3, label='cubic')     #etc
plt.xlabel('this is x label')                      # set the xlabel
plt.ylabel('this is y label')                      # set the ylabel
plt.title('Multi-lines in one figure')             # set the title
plt.legend()                         # show legend
```

![](../../.gitbook/assets/download-1.png)

### Column Chart

{% hint style="info" %}
**What to learn:**

* **Set figure size** 
* **Plot with numerical  variables and categorical variables**
* **Change column color**
* **Create horizontal bar chart**
{% endhint %}

```text
plt.figure(figsize = (8,6))                     # set the figure size

performance = [70,95, 61, 88,82]                # y_axis values
student = ['Mavin','Lily','Tim','Ben','Julian'] # x_axis values
y_pos = np.arange(len(student))                 # calculate number of "student"

plt.bar(y_pos,performance,color = 'orange')  # create bars, set the orange color 
plt.xticks(y_pos,student)       #Create names on the x-axis
plt.show()
```

![](../../.gitbook/assets/download-2.png)

#### Horizontal column chart

```text
# Create horizontal bars
plt.barh(y_pos, height)     # just add  a 'h' (horizontal)
plt.yticks(y_pos,student)   # we need to set students'name on the y-axis
```

![](../../.gitbook/assets/download.png)

