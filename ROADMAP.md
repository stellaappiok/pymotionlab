# Roadmap

A realistic, incremental version plan. Scope is deliberately conservative — each version should be shippable and usable on its own, rather than waiting for a "complete" release.

## v0.1 — Core kinematics (foundation)
- `RobotArm` class built from DH parameters
- Forward kinematics (position + orientation of end effector)
- Basic unit tests against hand-verified poses
- `pyproject.toml` set up, installable via `pip install -e .`

## v0.2 — Inverse kinematics
- Numerical IK solver (e.g. Jacobian pseudoinverse or CCD) for simple chains
- Analytical IK for common 2-DOF/3-DOF planar arms
- Tests comparing IK output back through FK to confirm round-trip accuracy

## v0.3 — Visualization
- Static 3D plot of arm pose (matplotlib)
- Simple animation of a joint-angle trajectory over time
- Example scripts in `examples/`

## v0.4 — Simulation & trajectories
- Joint-space trajectory generation (linear, trapezoidal velocity profile)
- Time-stepped simulation loop
- Basic collision checking (sphere/capsule approximations for links)

## v0.5 — Packaging & docs
- Publish first release to PyPI (or TestPyPI as a dry run)
- Documentation site (mkdocs or Sphinx) covering the public API
- CONTRIBUTING/CODE_OF_CONDUCT/SECURITY finalized, GitHub Actions CI running tests on every PR

## v0.6 — Hardware bridge (stretch)
- Serial/USB bridge to drive real servos from computed joint angles (Arduino/ESP32 target)
- Calibration helpers for mapping simulated angles to real servo ranges

## v1.0 — Stable API
- API frozen (semantic versioning from here on)
- Full test coverage on kinematics and simulation modules
- At least one worked end-to-end example (simulate → visualize → optionally drive real hardware)

## Beyond v1.0 (ideas, not commitments)
- Reinforcement learning environment wrapper (Gym-style) for arm control
- Basic computer-vision-based target tracking example
- Path planning around simple obstacles

## Non-goals (for now)
- Full physics simulation (contact dynamics, friction) — out of scope; this is a kinematics/visualization tool, not a physics engine
- ROS integration — may be revisited post-v1.0 if there's demand
