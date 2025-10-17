# Updating Your Course

This guide explains how to keep your course repository up-to-date with the latest extensions, packages, and template improvements.

## Quick Update

Run the update script:

```bash
./update-template.sh
```

This interactive script will guide you through updating:
1. Quarto extensions (r-wasm/live for pyodide)
2. Python packages (via pixi)
3. JupyterLite
4. Template improvements

## What Gets Updated

### 1. Quarto Extensions

**r-wasm/live** - Provides live-html format and pyodide support

Check current version:
```bash
cd WebBook
quarto list extensions
```

Update manually:
```bash
cd WebBook
quarto update extension r-wasm/live
```

### 2. Python Packages

Managed via `pixi.toml`. Key packages:
- quarto
- jupyterlite
- jupyterlite-pyodide-kernel
- ipython, ipykernel
- nbformat, nbclient

Update all:
```bash
pixi update
```

Update specific package:
```bash
pixi update quarto
```

### 3. JupyterLite

Rebuild after updating jupyterlite packages:

```bash
cd jupyterlite
pixi run jupyter lite build --contents content --output-dir dist
```

### 4. Template Improvements

The template itself receives updates. Two ways to stay current:

#### Automatic (Recommended)
- Template-sync GitHub Action runs monthly
- Creates pull requests with updates
- Review and merge when ready

#### Manual
Add template as remote and compare:

```bash
# First time only
git remote add template https://github.com/ANU-RSES-Education/EMSC-QuartoBook-Course.git

# Check for updates
git fetch template
git diff HEAD template/main

# See specific file changes
git diff HEAD template/main -- .github/workflows/publish.yml
```

## Update Frequency

**Recommended schedule:**

- **Quarto extensions**: Check at start of semester
- **Python packages**: Monthly or when issues arise
- **JupyterLite**: After package updates
- **Template**: Via automated PRs (monthly)

## Testing After Updates

Always test after updating:

```bash
# Build WebBook
pixi run quarto render WebBook

# Build WebSlides
pixi run quarto render WebSlides

# Check JupyterLite
cd jupyterlite && pixi run jupyter lite build --contents content --output-dir dist
```

## Troubleshooting Updates

### Extension Update Fails

```bash
# Remove and reinstall
cd WebBook
quarto remove extension r-wasm/live
quarto add r-wasm/live
```

### Package Conflicts

```bash
# Clean and reinstall
rm -rf .pixi
pixi install
```

### Build Breaks After Update

1. Check what changed:
   ```bash
   git diff pixi.lock
   ```

2. Revert to previous version:
   ```bash
   git checkout HEAD~1 pixi.lock
   pixi install
   ```

3. Report issue to template repository

## Version Tracking

Keep track of what you're running:

```bash
# Quarto version
quarto --version

# Python version
pixi run python --version

# List all packages
pixi list

# List extensions
cd WebBook && quarto list extensions
```

## See Also

- [Template Sync Documentation](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/template-sync.html)
- [Pixi Documentation](https://prefix.dev/docs/pixi/overview)
- [Quarto Extensions Guide](https://quarto.org/docs/extensions/)
