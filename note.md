# ROS2 Commands

## Node Commands
### Launching a node/executable from a package
  `ros2 run <package_name> <executeable_name>`

### List of running nodes
  `ros2 node list`

### Remapping value (node property) to another one
  `ros2 run turtlesim turtlesim_node --ros-args --remap __node:= my_turtle' 
(rename turtlesim node to my_turtle)

### Info of a node
  `ros2 node info <node_name>`

## Topic Commands
### List of topics
  `ros2 topic list -t`\n
-t adds the topic type to the output

### Read data being published into a topic
 `ros2 topic echo <topic_name>`

### Topic info
  'ros2 topic info <topic_name> --verbose'

### Show the interface (message type)
  `ros2 interface show <msg_type>`\n
msg_type shown via `ros2 topic list -t`

### Topic publish
`ros2 topic pub <topic_name> <msg_type> '<args>'`\n
`'<args>'` are the argument you pass in in the form of a YAML string: `"{linear: {x: 2.0}, angular: {y: 3.0}"`
