##Title: A collection of D3 learning materials
###### This repo is for collectiong the usefull resources of d3 learning

### Basic
[An intro to d3](http://www.samselikoff.com/tutorials/intro-to-d3-big-data.html)

+ Selection: in D3, the selection has two parts, the representation and the elements on the current DOM
	+ D3 knows the difference of the above two, when the data get joined.
+ Subselection: there are three subselections: enter, update and exit
+ Data is stored in the DOM: "when the elements are inserted into the DOM, D3 stores the data properties on the DOM nodes themselves"!

[D3 Wiki](https://github.com/mbostock/d3/wiki/Selections)
+ selection.append()  "It appends a new element with the specified name as the last child *OF* the parent selection *FOR* each element in the current selection, ..."

		var nums = [80, 53, 125, 200, 28, 97];
		var svg = d3.select('#d3Node').append('svg').attr('width',200).attr('height',200);
		var bars = svg.selectAll('rect').data(nums);
		bars.enter().append('rect');

	In above case, the `bars.enter()` is the representation and when `bars.enter().append('rect')` happens, we are appending it (`'rect'`) to the "parent selection" which in this case is the svg and the svg is being in the DOM. 

+selection.data([values[, key]]) Here the joined data is always an *array*, and the *array* can be "an array of an array (matrix)"