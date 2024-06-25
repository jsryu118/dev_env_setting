# frequently_used_lines
```
#xml
<remap from="/topic_name1" to="/topic_name2"/>
```
```
#xml
<node pkg="tf" type="static_transform_publisher" name="tf" args="x y z roll pitch yaw frame_id child_frame_id peroid[ms]"/>

<node pkg="tf" type="static_transform_publisher" name="tf" args="x y z qx qy qz qw frame_id child_frame_id peroid[ms]"/>
```

```
#!/bin/bash
rosrun tf static_transform_publisher x y z roll pitch yaw frame_id child_frame_id peroid[ms]

rosrun tf static_transform_publisher x y z qx qy qz qw frame_id child_frame_id peroid[ms]
```