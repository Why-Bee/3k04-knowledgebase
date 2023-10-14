- Dataflow graphical programming language for model-based design, and for simulation.
- It's best for modelling, simulating, and implementing embedded systems.
- A Simulink model is a description of a system using the block diagrams. a process called **code generation** converts the model into optimized, standalone C code.
- You can resize all blocks to fit with Space.
- You can pan by holding space and dragging with mouse
#### Simulink Embedded Coder
Generates the C code from Simulink models.

### Model
- Models are at the heart of Simulink's MDE.
- In Simulink, they are represented by block diagrams
	- Block: Performs a function that affects a signal
	- Line: Connects 2 blocks and transfers signals between them

#### Important Block Categories
To use blocks, press **CTRL + Shift + L** or click anywhere on the editor and start typing name of the block
1. Simulink Category
	1. Continuous: Linear, continuous time system elements that can add up to make a system (integrators, transfer functions)
	2. Discrete: Linear DT system elements
	3. Math Operations: allows to sum systems, gain systems, convolve systems etc
	4. Ports and Subsystems: A subsystem allows to group blocks together and make a 'black box' that can be reused later with input and output ports.
	5. Sink: Use to output signals (e.g. graph, scope, LCD)
	6. Source: Use to generate signals (e.g. step, impulse, sinusoid)
2. Simulink Coder Support Package for NXP-FRDM-K64F - Used to control on-board elements
![[Simulink Coder Support Package blocks.png]]
3. Stateflow- A way to model combinational and sequential logic
![[Stateflow Blocks.png]]

#### Modify Blocks
- You can change block names with F2.
- Modify block parameters by double-clicking a block

#### Connect blocks
- Click a port on a block, or an existing line, and click a model element (compatible ones are highlighted)
- Branch a signal by clicking CTRL while clicking a point on a line, and start dragging.
- For lines that are connected, an arrow can be seen. For lines that are not fully connected, the arrow is red
- Editor will try to optimise your connections by recommending block connections in blue. Click a blue connection to auto connect the blocks

#### Run simulation
- Use Simulation tab and pass stop time.
- Reason for using fixed time values for the solver in Tut 1.2: a solver converts a model to a set of ODEs, and solves them. If we have variable size, the step size is changed depending on rate of change of signal. Since we want to build for our micro, the step sizes are actually mapped to a clock on the board, and that can't have variable step sizes.