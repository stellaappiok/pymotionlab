# Contributing to PyMotionLab

Thanks for considering a contribution. This project is early-stage, so contributions of all sizes — typo fixes, tests, new features, docs are genuinely useful right now.

## Getting set up

```bash
git clone https://github.com/<your-username>/pymotionlab.git
cd pymotionlab
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -e ".[dev]"
```

Run the test suite to confirm your setup works:

```bash
pytest
```

## Project layout

```
pymotionlab/
├── pymotionlab/
│   ├── __init__.py
│   ├── kinematics/       # forward/inverse kinematics math
│   ├── arm.py            # RobotArm class
│   ├── simulate.py       # motion simulation engine
│   ├── visualize.py      # plotting/animation
│   └── io/               # config loading (DH params, arm specs)
├── tests/
├── examples/
├── docs/
├── pyproject.toml
└── README.md
```

## Coding standards

- **Style:** Black for formatting, Ruff for linting. Run `black . && ruff check .` before committing.
- **Type hints:** required on all public functions.
- **Docstrings:** Google style, required on all public classes/functions.
- **Naming:** `snake_case` for functions/variables, `PascalCase` for classes, matching standard Python convention.
- **No bare `except:`** — catch specific exceptions.

## Testing

- New features need at least one test in `tests/`.
- Kinematics functions should include a test against a known/hand-verified pose, not just "it runs without error."
- Run `pytest --cov=pymotionlab` to check coverage locally.

## Git workflow

1. Fork the repo and create a branch: `git checkout -b feature/short-description`
2. Make your change, with tests.
3. Run `black`, `ruff`, and `pytest` locally — CI will run them again, but catching issues early saves round-trips.
4. Open a pull request against `main` with a clear description of what changed and why.
5. One approving review is required before merge.

## Commit messages

Use a short imperative summary, e.g. `Add inverse kinematics for 3-DOF arm`, not `fixed stuff` or `updates`.

## Reporting bugs

Open an issue with:
- What you expected to happen
- What actually happened
- A minimal code sample that reproduces it
- Your Python version and OS

## Suggesting features

Open an issue describing the use case first, before submitting a PR. This avoids wasted work if the feature doesn't fit the project's direction, check `ROADMAP.md` for current priorities.

## Good first issues

Issues labeled `good-first-issue` on GitHub are scoped for newcomers to the codebase. Comment on one before starting work, to avoid duplicate effort.

## Questions

Open a discussion or issue — there's no separate chat/Discord yet.
