---
tags:
  - Log Analysis
  - Tools
---
Although not strictly for forensic purposes, **visualization tools**
such as the ones discussed here can be very useful for visualizing large
data sets. As forensic practitioners need to process more and more data,
it is likely that some of the techniques implemented by these tools will
need to be adopted.

## Programming Languages and Developer Toolkits

If you are building forensic tools, you probably want to start with one
of these:

### Java

Advantage: Portable and lots of good documentation out there.

Disadvantage: Programs are a bit verbose, and only offers about 1/2 the
performance of C

* [Graph Interface Library (GINY)](https://csbi.sourceforge.net/index.html) - Java
* [HyperGraph](https://hypergraph.sourceforge.net/) - Hyperbolic trees,
  in Java. Check out the home page. Try clicking on the logo...
* [InfoViz Toolkit](https://ivtk.sourceforge.net/) - Java, originally
  developed at INRA.
* [JGraphT](https://jgrapht.org/) - A Java visualization kit
  designed to be simple and extensible.
* [Perfuse](https://blokt.com/) - A Java-based toolkit for
  building interactive information visualization applications
* [VisAD](https://www.ssec.wisc.edu/~billh/visad.html#intro) - A Java
  component library for interactive and collaborative visualization.
* [Linguine Maps](https://github.com/psimakov/linguine-maps) -
  An open-source Java-based system for visualizing software call maps.
* [Zoomable Visual Transformation Machine](https://zvtm.sourceforge.net/index.html) -
  Java. Originally started at Xerox Research Europe.

### Python

Advantage: Portable

Disadvantage: Python is one of the slowest modern languages around and
doesn't work well with big data sets.

* Python with Tk
* Python with matplotlib
* Python with wxWidgets (not installed by default)
* [NetworkX](https://networkx.org/), a pure Python network layout
  program which uses matplotlib to do the actual graphing.

### Processing.org

Advantage: Programming language specifically developed for
visualization; compiles to java byte code

Disadvantage: Very oddball

* [processing.org](https://processing.org/) and

### JavaScript

Browsers are now very fast and there are a large number of data plotting
systems built on JavaScript. Check out:

* [processingjs.org](https://github.com/processing-js/processing-js)
* [Highcharts JS](https://www.highcharts.com/)
* [D3 - Data Driven Documents](https://d3js.org/) - A visualization library for
  the Web.
* [KeyLines](https://cambridge-intelligence.com/) - Commercially licensed visualization
  library for networks/graphs.

### C/C++

* [The Visualization Toolkit](https://vtk.org/) - C++ multi-platform
  with interfaces available for Tcl/Tk, Java and Python.

## Applications

Most of these applications can be used to do visualization

Crystal Space 3D

<!-- -->

Panda#D

### Data Plotting Applications

* <https://ploticus.sourceforge.net/>
* <http://www.gnuplot.info/>
* <https://tulip.labri.fr/site/>

### Graph and (Social) Network Visualization

* [Cytoscape](https://cytoscape.org/) - Cytoscape is an open source
  software platform for visualizing complex networks and integrating
  these with any type of attribute data.
* [Graphviz](http://www.graphviz.org/) - Originally developed by the
  AT&T Information Visualization Group, designed
  for drawing connected graphs of nodes and edges. Neato is a similar
  system but does layout based on a spring model. Can produce output as
  PostScript, PNG, [GIF](gif.md), or as an annotated graph file with
  the locations of all of the objects — ideal for drawing in a GUI. Runs
  from the command line on [Unix](unix.md),
  [Windows](windows.md) and [Mac](mac_os_x.md), although
  there is also a [MacOS GUI version](http://www.pixelglow.com/graphviz/).
* [NodeXL](https://nodexl.com/) - Free/open excel add-in extends the spreadsheet
  with network metrics and visualizations. (Only runs on Windows)
* [Gephi](https://gephi.org/) -Gephi is an interactive visualization and
  exploration platform for all kinds of networks and complex systems,
  dynamic and hierarchical graphs

<!-- -->

* [graph-tool](https://graph-tool.skewed.de/) is an efficient Python module for
   manipulation and statistical analysis of graphs (a.k.a. networks).
* <https://igraph.org/> - Integrates with R.
* <https://socnetv.org/> - "Social Networks Visualizer
  (SocNetV) is a flexible and user-friendly tool for the analysis and
  visualization of Social Networks."
* [NetDraw](https://sites.google.com/site/netdrawsoftware/welcome) -
  a free program written by Steve Borgatti for visualizing both 1-mode and
  2-mode social network data.
* [Pajek](http://mrvar.fdv.uni-lj.si/pajek/) - Windows program for drawing
  large networks.
* [Social Network Image Animator (SoNIA)](https://sourceforge.net/projects/sonia/) -
  Originally developed at Stanford. Written in Java. Makes movies.
* [Walrus](https://www.caida.org/catalog/software/walrus/) -
  A 3-d graph network exploration tool. Employs 3D hyperbolic displays and
  layout based on a user-supplied spanning tree.
* [AfterGlow](https://afterglow.sourceforge.net/) - A tool to simplify the
  generation of network graphs in GraphViz, Gephi, etc. Designed for
  security visualizations.
* <https://tulip.labri.fr/site/> - Tulip is an information
  visualization framework dedicated to the analysis and visualization of
  relational data.

See also:
<https://en.wikipedia.org/wiki/Social_network_analysis_software>

Reas govisual diagram editor reas.com gdf.net

### Commercial Graphic Applications and Tools

* [aiSee Graph Layout Software](https://www.absint.com/aisee/) - Supports 15
  layout algorithms, recursive graph nesting, and easy printing. Runs on
  [Windows](windows.md), [Linux](linux.md),
  [Solaris](solaris.md), [NetBSD](netbsd.md), and
  [MacOS](mac_os_x.md). 30-day trial and free registered versions
  available. Academic pricing available.
* [Geomantics](https://www.geomantics.com/) - Geographical, Visualization
  and Graphics software. Runs on [Windows](windows.md).
* [Graphis 2D and 3D graphing software](http://www.kylebank.com/) - Runs
  on [Windows](windows.md). Free 30-day evaluation copy
  available.
* [OpenViz](https://www.avs.com/openviz/) and [PowerViz](https://www.avs.com/examples/openviz/real-time-monitoring-for-larger-than-life-datasets/) -
  Both from Advanced Visual Systems, super high-end visualization toolkits.
  \$\$\$\$
* [Tom Sawyer Software](https://www.tomsawyer.com/) Analysis,
  Visualizaiton, and Layout programs. - Heavy support for drawing
  graphs. Beautiful gallery. ActiveX, Java, C++ and .NET editions.
* [NetMiner](http://www.netminer.com/) - A comprehensive tool for Social
  Network Analysis. Runs on Windows, with a Linux version under
  development. \$35 for "Express" student version, \$250 for
  "Professional" student version, \$950 for "Normal" "Professional"
  version.
* [UCINET](https://sites.google.com/site/ucinetsoftware/home) -
  A comprehensive package for the analysis of social network data as well as
  other 1-mode and 2-mode data.

### Unclassified

* [Gravisto: Graph Visualization Toolkit](https://github.com/Gravisto/Gravisto) -
  An editor and toolkit for developing graph visualization algorithms.
* [TouchGraph](https://touchgraph.sourceforge.net/) -
  Library for building graph-based interfaces.

## See Also

* [Network Data Visualizations](network_data_visualizations.md)

## External Links

* [GNU Free Software directory: Category/Science/scientific-visualization](https://directory.fsf.org/wiki/Category/Science/scientific-visualization)
* [INSNA's web page of Computer Programs for Social Network Analysis](https://www.insna.org/)
* [Omnigator](https://ontopia.net/omnigator/models/index.jsp)
* [VisANT](http://visant.bu.edu/)
* [TouchGraph](https://sourceforge.net/projects/touchgraph/)

CAIDA has 15+ years of work visualizing Internet topologies. You may
find their tools to be useful:

* <http://www.caida.org/tools/visualization/>
* <https://www.caida.org/catalog/media/visualizations/>
* <https://www.caida.org/catalog/software/walrus/gallery1/>
* <https://www.caida.org/projects/as-core/>
