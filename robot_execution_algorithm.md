# 🚦 Detailed Execution Algorithm

1. **Receive Product Request**
   - Order is received from an external system (e.g. ERP).
   - Product availability is checked in the inventory database.

2. **Identify Product Location**
   - Retrieve the location in the warehouse (e.g., Aisle B, Shelf 2, Column 3).
   - Convert physical location to coordinates on the warehouse map.

3. **Plan Path to Product**
   - Use SLAM or pathfinding (A* or Dijkstra) to plan route.
   - Account for static and dynamic obstacles.

4. **Navigate to Product**
   - Robot moves along the path using wheels.
   - Sensors (LiDAR, Ultrasonic, IMU) used for localization and obstacle avoidance.

5. **Pick Product**
   - Robot aligns itself to product shelf.
   - Product is detected using camera and computer vision.
   - Robotic arm uses inverse kinematics to reach and grip the product.
   - Confirmation through weight sensor or camera.

6. **Deliver Product**
   - Plan new path to delivery station.
   - Navigate and avoid any obstacles.
   - Place product in delivery bay.

7. **Post-Delivery Action**
   - If another task exists, repeat the process.
   - If battery is low, return to charging dock.
   - If idle, return to base station.

8. **Error Handling**
   - Monitor sensors at each step.
   - Replan if product not found, collision detected, or delivery failed.