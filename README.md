# Resource Allocation Graph (RAG) Simulator

A Python desktop application to visualize Resource Allocation Graphs (RAG), simulate Banker's Algorithm for deadlock avoidance in single-instance resource allocation, and detect deadlocks due to circular wait conditions in multiple-instance resource allocation scenarios. Built with Tkinter for GUI, NetworkX for graph modeling, and Matplotlib for visualization.

## Features

- **Two simulation modes:**
  - Single Instance Resource Allocation using Banker's Algorithm.
  - Multiple Instances Resource Allocation with Circular Wait detection.
- Interactive GUI with:
  - Input for number of processes and resources.
  - Editable allocation, maximum need, and request matrices.
  - Visualization of resource allocation graphs with color-coded nodes and edges.
  - Visualization of safe sequences or deadlock cycles.
- Dynamic graph visualization using NetworkX and Matplotlib.
- Clear display of allocation and request edges with labels and edge coloring.
- User-friendly controls for running algorithms, resetting inputs, and navigating to the main menu.
- Background customization with image support or fallback solid color.

## Installation

Ensure you have Python 3.x installed with the following dependencies:

```

pip install tkinter
pip install matplotlib
pip install networkx
pip install pillow

```

## Usage

Run the main script:

```

python rag_simulator.py

```

- Select between "Single Instance (Banker's Algorithm)" or "Multiple Instances (Circular Wait)".
- Enter the number of processes and resources.
- Fill in the allocation, max need (Banker's), or allocation/request (Circular Wait) matrices.
- For Banker's algorithm, also specify available resources.
- Click to run the algorithm or check deadlock.
- Visualize the resulting resource allocation graph and algorithm results interactively.

## Code Structure

- `RAGSimulator` — Main menu and background setup.
- `BankersAlgorithmGUI` — Implements the Banker's Algorithm simulation with graph visualization and animation for safe sequence.
- `CircularWaitGUI` — Implements detection of circular wait deadlocks on multiple resource instances with graph highlighting.

## Technical Notes

- Uses `tkinter.Label` with `place()` to set a background image or uses a fallback solid color if the image is missing.
- NetworkX directed graphs represent processes (blue circles) and resources (red squares).
- Edges represent allocation (solid black) and request (dashed red).
- Matplotlib embedded in Tkinter via `FigureCanvasTkAgg` for interactive graph drawing.
- Threading used to animate safe sequence highlighting without blocking the UI.
- Error handling for invalid inputs with informative message boxes.
