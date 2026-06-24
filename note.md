# ROS2 Commands
* Interface is the I/O of a type
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

## Topic (PubSub) Commands
### List of topics
  `ros2 topic list -t`<br>
-t adds the topic type to the output

### Read data being published into a topic
 `ros2 topic echo <topic_name>`

### Topic info
  'ros2 topic info <topic_name> --verbose'

### Show the interface (message type)
  `ros2 interface show <msg_type>`<br>
msg_type shown via `ros2 topic list -t`

### Topic publish
  `ros2 topic pub <topic_name> <msg_type> '<args>'`<br>
`'<args>'` are the argument you pass in in the form of a YAML string: `"{linear: {x: 2.0}, angular: {y: 3.0}"`

## Service (Request/Respond) Commands
### Service type  
  `ros2 service type <service_name>` <br>
request/response data structure

### Service list
  `ros2 service list -t`

### Service info
  `ros2 service info --verbose <service_name>`

### Find service of type (via `ros2 interface show`)
  `ros2 service find <type_name>`

### Call a service
  `ros2 service call <service_name> <service_type> <arguments>`

### Echo a service
  `ros2 service echo <service_name | service_type> <arguments>`

## Parameters (aka node settings)

### List parameters
  `ros2 param list`

### Get the type and value of a param
  `ros2 param get <node_name> <parameter_name>`

### Set the value of a param (at runtime)
  `ros2 param set <node_name> <parameter_name> <value>`

### View all node's current param values
  `ros2 param dump <node_name>`

### Load param from a file
  `ros2 param load <node_name> <parameter_file>`

### Load param file on node startup
  `ros2 run <package_name> <executable_name> --ros-args --params-file <file_name.yaml>`

## Action (topics + services w/ steady feedback, cancelable action)
the node (ex: turtlesim) responds and provides feedback for the action (in action server) <br>
another node (ex: teleop_turtle) has the same action name under client, it sends goal for that action <br>

### Get all action in ROS graph
`ros2 action list -t`

### Check type of action
`ros2 action type <action_name>`

### Check info
`ros2 action info <action_name>`

### Check type (same as above in topic)
### Send goal
`ros2 action send_goal <action_name> <action_type> <values>` <br>
`<values>` should be in yaml

### See data between action client and server
`ros2 action echo <action_name> <optional arguments/action_types>`
