# Basic Plot

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

![Column Chart](../../.gitbook/assets/download-2%20%281%29.png)

#### Horizontal Column Chart

```text
# Create horizontal bars
plt.barh(y_pos, height)     # just add  a 'h' (horizontal)
plt.yticks(y_pos,student)   # we need to set students'name on the y-axis
```

![Horizontal Column Chart](../../.gitbook/assets/download.png)

{% hint style="info" %}
**What to learn:**

* **The difference of Stacked Column Chart and Grouped Column Chart**
* **:Plot two groups of bar on one figure**
* **Choose  the proper chart** 
{% endhint %}

#### Stacked Column Chart

```text
labels =['G1', 'G2', 'G3', 'G4']
male_avg = [1.80,1.75, 1.84,1.7]
female_avg =[1.75, 1.6, 1.70, 1.53]

width =0.4   # set the width of the bars

fig, ax = plt.subplots()
ax.bar(labels, male_avg, width,  label ='Male')
ax.bar(labels, female_avg, width,  bottom=  male_avg,
       label='Female')
       
ax.set_ylabel('Average Height')
ax.set_title('Height by group and gender')
ax.legend()

plt.show()
```

![Stacked Bar Chart](../../.gitbook/assets/download-2.png)

**Obviously, this is a bad choice.** Stacked bar can't show  the trends nor difference clearly. Meanwhile. the stack makes y\_axis value non-sense.  Nobody grows to 3.5 metre!!

So we should alternate to  **grouped bar chart.**

#### **Grouped Bar Chart**

```text
width =0.4
x = np.arange(len(labels))  # the label locations

fig, ax = plt.subplots()
rects1 = ax.bar(x - width/2, male_avg, width, label='Male')
rects2 = ax.bar(x + width/2, female_avg, width, label='Female')

ax.set_xticks(x)
ax.set_xticklabels(labels)  # set the categorical variable on x_axis
       
ax.set_ylabel('Average Height')
ax.set_title('Height by group and gender')
ax.legend()

plt.show()
```

![Grouped Bar Chart](../../.gitbook/assets/download-3.png)

Now, it looks  much better  and makes sense. Matplotlib is very basic way to illustrate relationship. 

Later you will see shorter and simpler solutions in [Seaborn](../seaborn/), [Bokeh, ](../bokeh.md)and [Plotly](../plotly.md).

### Histogram Chart

```text
x = [1,22,19,44,5,6,77,8,3,10,31,32,33,34,35,36,37,28,49,30,100]
num_bins = 10

plt.figure(figsize = (8,6))

# Create hist, set color and color alpha (transparency)
n, bins, patches = plt.hist(x, num_bins, facecolor='blue', alpha=0.5)

plt.title('Histogram chart when bins = 10')  # set title name
plt.ylabel('Count')                          # set ylabel name

plt.show()
```

![](../../.gitbook/assets/download%20%281%29.png)

