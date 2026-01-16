# ABC+ Submodule Integration Guide

This document explains how to integrate the ABC+ specification into your projects using Git submodules.

## Initial Setup (First Time)

### 1. Push the Spec to GitHub

First, create the `abc-plus-spec` repository on GitHub, then:

```bash
cd abc-plus-spec
git remote add origin https://github.com/leedale30/abc-plus-spec.git
git push -u origin main
```

### 2. Add as Submodule to Your Project

In your other projects (like abc-to-xml-converter):

```bash
cd your-project
git submodule add https://github.com/leedale30/abc-plus-spec.git abc-plus-spec
git commit -m "Add ABC+ spec as submodule"
git push
```

## Workflow

### Updating the Spec

When you make changes to ABC+:

```bash
cd abc-plus-spec
# Make your changes to SPECIFICATION.md, etc.
git add .
git commit -m "Add new directive: %%example"
git push
```

### Pulling Spec Updates into Projects

In projects that use the submodule:

```bash
cd your-project
git submodule update --remote abc-plus-spec
git add abc-plus-spec
git commit -m "Update ABC+ spec to latest"
git push
```

### Cloning a Project with Submodules

When cloning a project that contains the submodule:

```bash
git clone --recurse-submodules https://github.com/leedale30/your-project.git
```

Or if already cloned:

```bash
git submodule update --init --recursive
```

## Pinning to a Specific Version

To pin to a specific version of the spec:

```bash
cd abc-plus-spec
git checkout v1.0.0  # Use a specific tag
cd ..
git add abc-plus-spec
git commit -m "Pin ABC+ spec to v1.0.0"
```

## File Structure After Integration

```
your-project/
├── abc-plus-spec/          # Submodule
│   ├── SPECIFICATION.md
│   ├── schema/
│   └── examples/
├── your-code/
└── .gitmodules             # Auto-generated submodule config
```

## Reading the Spec in Your Code

### Python Example

```python
import json
import os

spec_path = os.path.join(os.path.dirname(__file__), 'abc-plus-spec', 'schema', 'directives.json')
with open(spec_path) as f:
    ABC_PLUS_SCHEMA = json.load(f)
```

### JavaScript Example

```javascript
const spec = require('./abc-plus-spec/schema/directives.json');
```
