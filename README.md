# GraphvizAnim


__Demo for @fantasticlife__: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ouseful-demos/GraphvizAnim/HEAD?filepath=examples%2Fdot-anim.ipynb)

[![Build Status](https://travis-ci.org/mapio/GraphvizAnim.png?branch=master)](https://travis-ci.org/mapio/GraphvizAnim) [![Binder](https://img.shields.io/badge/launch-binder-ff69b4.svg?style=flat)](https://mybinder.org/v2/gh/mapio/GraphvizAnim/master?filepath=examples/heapsort.ipynb) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.1037283.svg)](https://doi.org/10.5281/zenodo.1037283)


GraphvizAnim is a tool to create simple animated graph visualizations; it is
just a proof of concept, aimed mainly at teaching purposes. It is based on
[Graphviz](http://www.graphviz.org/) for the graph rendering part and on
[ImageMagick](http://www.imagemagick.org/) for the animated gif generation. You can [run the heap sort animation](https://mybinder.org/v2/gh/mapio/GraphvizAnim/master?filepath=examples/heapsort.ipynb) on-line using [binder](http://mybinder.org/).

<p align="center">
<img src="examples/dfv.gif"/>
<img src="examples/heapsort.gif"/>
</p>

A *graph animation* is just a sequence of *steps*, a step is in turn one or
more *actions* such as: *add*, *hilight*, *label*, *unlabel* or *remove* a
*node*, and  *add*, *hilight*, or *remove* an *edge*. Animations can be built
by invoking suitable methods of a `gvanim.Animation` object (in a Python
program), or by parsing a simple text file (that, in turn, can be generated by
a program in any language).

The [examples](examples) folder contains few instances of such approaches.
After installing the package with `python setup.py install`, or using

	pip install GraphvizAnim

you can generate an animated depth first visit (in a 3-regular random graph of
6 nodes) by running

	python examples/dfv.py

or you can generate the simple animation described in
[simple.txt](examples/simple.txt) as

	python -m gvanim examples/simple.txt simple

You can generate an [Erdős–Rényi](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93R%C3%A9nyi_model) graph (with 10 nodes and edge probability
1/10) by running

	cd examples
	gcc -o er er.c
	./er | python -m gvanim er

Finally, you can obain an interactive visualization of the *heap sort*
algorithm using [Jupyter](http://jupyter.org/) by running

	cd examples
	jupyter notebook heapsort.ipynb

and running all the cells in order; or you can give a try to
[binder](http://mybinder.org) and watch the above animation
[actually running](https://mybinder.org/v2/gh/mapio/GraphvizAnim/master?filepath=examples/heapsort.ipynb) on-line.
