# PyMotionLab

A Python library for simulating, visualizing, analyzing robotic arm motion and built for learning and for real use.

PyMotionLab lets you define a robot arm's kinematic structure, compute forward and inverse kinematics, simulate motion over time, and visualize the result without needing physical hardware or a heavyweight robotics stack.

## Why PyMotionLab

Most beginner-friendly robotics tools are either too simplified to teach real concepts, or too complex (ROS, full physics engines) to get started with quickly. PyMotionLab aims for the middle: real kinematics math, a clean API, and visual feedback, in a library small enough to read end-to-end.

## Features (current + planned)

- [x] Define robot arms via DH parameters or simple link/joint specs
- [x] Forward kinematics
- [ ] Inverse kinematics (analytical + numerical)
- [ ] 2D/3D visualization of arm pose and motion
- [ ] Trajectory generation and animation
- [ ] Basic collision checking
- [ ] Arduino/serial bridge for driving real servos

See `ROADMAP.md` for the full version plan.

## Installation

```bash
pip install pymotionlab
```

(Not yet published — for now, clone and install locally:)

```bash
git clone https://github.com/<your-username>/pymotionlab.git
cd pymotionlab
pip install -e .
```

## Quick example

```python
from pymotionlab import RobotArm

arm = RobotArm.from_dh_params([
    {"a": 0, "alpha": 90, "d": 0.1, "theta": 0},
    {"a": 0.3, "alpha": 0, "d": 0, "theta": 0},
    {"a": 0.25, "alpha": 0, "d": 0, "theta": 0},
])

pose = arm.forward_kinematics(joint_angles=[0, 45, -30])
print(pose.position, pose.orientation)
```

## Documentation

Full documentation lives in `docs/` (in progress). Start with:

- `PyMotionLab_Handbook.docx` — architecture, math background, coding standards, roadmap
- `CONTRIBUTING.md` — how to contribute
- `ROADMAP.md` — where the project is headed

## Status

Early-stage, actively developed. APIs may change without notice until v1.0.

## License

MIT — see `LICENSE`.

## Contributing

Contributions are welcome. See `CONTRIBUTING.md` for setup instructions and coding standards, and `CODE_OF_CONDUCT.md` for community expectations.
