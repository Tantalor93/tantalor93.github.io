---
layout: post
title: "Data visualization in Go"
categories: misc
---

During the development of [dnspyre](https://tantalor93.github.io/dnspyre/), a DNS load testing tool written in Go,
I realized it would be beneficial to provide a way to visualize results using line graphs, histograms, bar charts, etc.
This led me to the [gonum/plot](https://github.com/gonum/plot) library.

<div class="image">
    <a href="https://github.com/gonum/plot" target="_blank">
        <img src="{{ site.baseurl }}/assets/images/gonumplot-blog-logo.svg" alt="gonum/plot logo" >
    </a>
</div>
<figcaption>gonum packages logo</figcaption>

`gonum/plot` is a powerful Go library for plotting and visualization of data. It supports a wide
range of plot types, from simple lines and scatter plots to more complex histograms and box plots. The library's flexibility
even allows for easy combinations of multiple graphs, making it straightforward to overlay data for a more comprehensive view.
You can check out various [examples](https://github.com/gonum/plot/wiki/Example-plots) on the library's page. 

In dnspyre, I used the library for example to plot a histogram of response latencies. Check out the code sample and
resulting plot below:

```
// Datapoint one datapoint of benchmark (single DNS request).
type Datapoint struct {
	Duration time.Duration
	Start    time.Time
}

func plotHistogramLatency(file string, times []dnsbench.Datapoint) {
	if len(times) == 0 {
		// nothing to plot
		return
	}
	var values plotter.Values
	for _, v := range times {
		values = append(values, float64(v.Duration.Milliseconds()))
	}
	p := plot.New()
	p.Title.Text = "Latencies distribution"

	// Rice Rule
	numBins := int(2 * math.Cbrt(float64(len(times))))

	hist, err := plotter.NewHist(values, numBins)
	if err != nil {
		panic(err)
	}
	p.X.Label.Text = "Latencies (ms)"
	p.X.Tick.Marker = hplot.Ticks{N: 5, Format: "%.0f"}
	p.Y.Label.Text = "Number of requests"
	p.Y.Tick.Marker = hplot.Ticks{N: 5, Format: "%.0f"}
	hist.FillColor = color.RGBA{R: 175, G: 238, B: 238, A: 255}
	p.Add(hist)

	if err := p.Save(6*vg.Inch, 6*vg.Inch, file); err != nil {
		fmt.Fprintln(os.Stderr, "Failed to save plot.", err)
	}
}
```

<div class="image">
    <img src="{{ site.baseurl }}/assets/images/gonumplot-blog-histogram.svg" alt="gonum/plot histogram" >
</div>
<figcaption>example of histogram visualization</figcaption>

The library provides two main packages: `plot` and `plotter`. The `plot` package offers an API for creating plots and basic
drawing primitives, while the `plotter` package implements commonly used graphs such as lines, scatter plots, box plots,
histograms, and more.

If you’re looking for a reliable way to add data visualization to your Go projects, I highly recommend exploring `gonum/plot`
library. I found it both efficient and versatile for creating a variety of visualizations, and it was easy to work with.
