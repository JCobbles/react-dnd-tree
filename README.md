# React drag-and-drop for directed graphs

## Features

- Represent any directed graph
  - Multiple root nodes possible
  - Nodes can have multiple parents
- Drag and drop node movement
- Edges between nodes can be drawn intuitively
- Edges can be deleted by selecting them and clicking the Delete key
- Graph can be panned and zoomed

![example directed graph](https://github.com/JCobbles/react-dnd-tree/raw/master/dag.png)


## Install
- `npm i --save react-dnd-tree`


## Usage

```
import DnDTree from 'react-dnd-tree'
```
### Using SSR (Server-Side Rendering)

```
function Component(props) {

  const DnDTree = require('react-dnd-tree').default
  return (
    <DnDTree
      nodes={model.nodes}
      edges={model.edges}
      height={400}
      edgeDraw
      errorHandler={errorHandler}
      updateHandler={updateHandler}
      edgeType='curve'
      onNodeSelected={nodeSelected}
    />
  )
}
```

#### Options

- `nodes`: list of node objects of format { label }
- `edges`: list of edge objects of format { from: int, to: int } where from, to are indices into the nodes list
- `edgeDraw`: default=True, whether you can draw edges between nodes
- `errorHandler`: callback function taking an error message
- `onNodeSelected`: callback function taking the selected node object
- `updateHandler`: callback taking (nodes, edges) every time the user updates the graph
- `edgeType`: (curve | line) the line interpolation style between nodes
