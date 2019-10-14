# Maze
&ensp;This project is based on the given code [maze](https://github.com/zilinglius/maze).
<pr>
## 1. Introduction

&ensp;**Function:**</br>

- **Create Maze.** Choose Maze type and create.
- **Animated.** You can choose to create maze animatedly.
- **Solve.** The maze will start finding ways itself.

## 2. JavaScript

### 2.1 Function overview
| Function | Usage 
| :-: | -
|drawMaze(), drawBlock()| draw maze1 and maze 2
|getFNeighbours(), getENeighbours() | get accessible points from four or eight direction
|getNeighbours() | use when create maze1, get 2 points each time
|solveMaze1(), solveMaze2()| end when the start point meet the goal, else find accessible direction and go back when no way to go.
|getCursorPos | get where the mouse clicked and write down the start and end point.
|createMaze1()|update score and level, only for one player widget
|createMaze1NonAni()|use a while(1) loop to create the canvas at one time
|createMaze2()|use `Math.random()` to create points randomly according to given density.
|createMaze2NonAni()|use a for loop to create the canvas at one time
|onCreate()|when the `create` button clicked, get the `cols`, `rows` and `MazeType` to create canvas.
|onSltType()|if the `Maze 2` is choosen, the disable button `density` should be enabled

### 2.2 Solving Algorithm
&emsp;**Maze 1:** Consider that every time there is only two direction to choose, everytime, put the accessible points `(x,y)` into array, use `.sort()` to find the point nearest to the goal. 
&emsp;**Maze 2:** Decide to use A* to find the road. As the time is limited, it now use the same algorithm as maze one.


### 2.3 Adjust
&emsp;Use `window.onresize = function()` to check whelther the window size changed, if changed, adjust the property of element `canvas`.


## 3. HTML & CSS
Use a new CSS Frameworks `BootStrap` to rewrite the web interface.

[![KST9ER.md.jpg](https://s2.ax1x.com/2019/10/14/KST9ER.md.jpg)](https://imgchr.com/i/KST9ER)
### 2.1 head
&emsp;Add the responsive viewport `<meta>` tag.
&emsp;Paste the stylesheet `<link>` here to load our CSS.
&emsp;Place the following `<script>s`  right before the closing `</body>` tag to enable them.</br>


### 2.2 body

&emsp;Include a `navbar`, `input groups`, the main `canvas` and a `footer`.
#### 2.2.1 navbar

[![KSTSb9.md.jpg](https://s2.ax1x.com/2019/10/14/KSTSb9.md.jpg)](https://imgchr.com/i/KSTSb9)



#### 2.2.2 input-group

[![KSozDJ.md.jpg](https://s2.ax1x.com/2019/10/14/KSozDJ.md.jpg)](https://imgchr.com/i/KSozDJ)

&emsp; Use several `<div class="col-X"> <\div>` to optimize the layout.

&emsp; **Maze Type:** Input groups include support for custom selects. Use `<select> </select>` and `<option> </option>` to create options.

&emsp; **Columns, Rows, Density:** Use `<label> </label>` and `<input> <\input>` .

&emsp; **Animated:** Use an `<input> <\input>` which  `type="checkbox"` .

&emsp; **Create:** A simple `button`.


#### 2.2.3 canvas
&emsp; After click Create, the grey window now will show `maze`. Use `ctx.scale(s, s)` in `html` to scale the maze to ensure the width unchanged.
