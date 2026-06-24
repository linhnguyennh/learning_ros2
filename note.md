# ROS2 Commands

### Launching a node/executable from a package
  `ros2 run <package_name> <executeable_name>`

### List of running nodes
  `ros2 node list`

### Remapping value (node property) to another one
  `ros2 run turtlesim turtlesim_node --ros-args --remap __node:= my_turtle #(rename turtlesim node to my_turtle)`

### Info of a node
  `ros2 node info <node_name>`
