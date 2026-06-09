# 52 - Composite Actions

Composite actions allow you to combine multiple workflow steps into a single action.

## Key Features
- **Simplified YAML:** Reduce boilerplate in your main workflows.
- **Cross-Platform:** Can run on any OS supported by the steps.
- **No Docker Required:** Runs directly on the runner.

## Structure (`action.yml`)
```yaml
name: 'Hello World'
description: 'Greet someone'
inputs:
  who-to-greet:
    description: 'Who to greet'
    required: true
    default: 'World'
runs:
  using: "composite"
  steps:
    - run: echo "Hello ${{ inputs.who-to-greet }}"
      shell: bash
```

## Exam Tips
- Every step in a composite action MUST specify a `shell` (e.g., `shell: bash`).
- Composite actions are great for wrapping a series of `run` commands.
- They are different from Docker actions which run in a container.
