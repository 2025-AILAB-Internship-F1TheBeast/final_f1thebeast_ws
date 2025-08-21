# F1TENTH Autonomous Racing System

## Installation

### Clone Repository with Submodules

```bash
git clone --recursive https://github.com/2025-AILAB-Internship-F1TheBeast/final_f1thebeast_ws.git
```

Or if already cloned:
```bash
git submodule update --init --recursive
```

## Usage

### Perception
Localization and environment sensing components.

```bash
ros2 launch particle_filter_cpp localize_sim_launch.py    # Vehicle localization using particle filter
ros2 launch obstacle_detection_pkg obstacle_detection.launch.py    # Obstacle detection and mapping
```

### Planning
Path planning and trajectory generation.

```bash
ros2 launch local_planner_pkg local_planner.launch.py                   # Local path planning
ros2 launch local_planner_pkg local_planner.launch.py sim_mode:=true    # For simulation mode
```

### Control
Vehicle control and path following.

```bash
ros2 launch path_follower_pkg path_follower.launch.py                   # Path following controller
ros2 launch path_follower_pkg path_follower.launch.py sim_mode:=true    # For simulation mode
```

### Simulation
Simulation environment for testing.

```bash
ros2 launch f1tenth_gym_ros gym_bridge_launch.py    # F1TENTH simulation environment
```

### Simple Driving
Basic gap-following algorithm for simple autonomous driving.

- Use `src/base_ws/basecode_follow_the_gap/`

## Map Configuration

When changing maps, update the following packages:
- `src/perception_ws/particle_filter_cpp/` - Localization maps
- `src/perception_ws/obstacle_detection_pkg/` - Detection parameters
- `src/planning_ws/local_planner_pkg/` - Planning maps
- `src/base_ws/base_f1tenth_gym_ros/f1tenth_gym_ros/` - Simulation maps