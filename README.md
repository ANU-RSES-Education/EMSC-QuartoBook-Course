# EMSC Quarto Course Template

A comprehensive GitHub template for creating interactive, web-based quantitative Earth Science courses.

## 📚 Features

- **Quarto Book** - Beautiful, searchable course notes with live Python execution
- **Reveal.js Slides** - Professional presentation slides embedded in your course
- **JupyterLite** - Full Jupyter environment running in the browser
- **Pyodide Integration** - Run Python code directly in web pages
- **Automated Deployment** - Push to deploy via GitHub Actions
- **Template Sync** - Automatically receive updates and improvements

## 🚀 Quick Start

### 1. Create Your Course

Click **"Use this template"** above to create your own course repository.

### 2. Read the Documentation

**📖 [Full Documentation](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/)**

The documentation covers:
- [Getting Started Guide](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/getting-started.html)
- [Configuration Options](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/configuration.html)
- [Customization Guide](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/customization.html)
- [Template Sync](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/template-sync.html)
- [Troubleshooting](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/troubleshooting.html)

### 3. Install Dependencies

Using [Pixi](https://prefix.dev/docs/pixi/overview) (recommended):

```bash
pixi install
pixi run quarto render WebBook
```

Or with Python/pip:

```bash
# Install Quarto from https://quarto.org
pip install jupyterlite jupyterlite-pyodide-kernel ipython ipykernel
quarto render WebBook
```

### 4. Customize Your Course

1. Edit `WebBook/_quarto.yml` - Update title, author, and settings
2. Add content to `WebBook/` - Create your lectures and materials
3. Create slides in `WebSlides/` - Build presentations
4. Push to deploy - GitHub Actions automatically builds and publishes

## 📖 Examples

Courses built with this template:

- [EMSC-3022: Planetary Sciences](https://github.com/ANU-RSES-Education/EMSC-3022)
- [Zero to Python for Earth Sciences](https://github.com/ANU-RSES-Education/Zero-2-Python-for-Earth-Sciences)

## 🛠 Technology Stack

- [Quarto](https://quarto.org/) - Scientific publishing system
- [Pixi](https://prefix.dev/docs/pixi/overview) - Package manager
- [JupyterLite](https://jupyterlite.readthedocs.io/) - Browser-based Jupyter
- [Pyodide](https://pyodide.org/) - Python in WebAssembly
- [Reveal.js](https://revealjs.com/) - HTML presentations
- GitHub Actions - Automated deployment

## 📝 Repository Structure

```
EMSC-QuartoBook-Course/
├── docs/                    # Template documentation
├── WebBook/                 # Course book content
│   ├── _quarto.yml         # Book configuration
│   ├── assets/             # Images, CSS, logos
│   └── *.qmd               # Course pages
├── WebSlides/              # Presentation slides
├── jupyterlite/            # JupyterLite configuration
├── .github/workflows/      # Automated build & deploy
├── pixi.toml              # Environment configuration
└── build.sh               # Local build script
```

## 🔄 Keeping Up to Date

This template includes automatic synchronization:

- **Automatic**: Monthly checks for template updates
- **Manual**: Trigger sync anytime from Actions tab
- **Safe**: Creates pull requests for review before merging

See the [Template Sync documentation](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/template-sync.html) for details.

## 💡 Getting Help

- **Documentation**: [anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/](https://anu-rses-education.github.io/EMSC-QuartoBook-Course/docs/)
- **Issues**: [GitHub Issues](https://github.com/ANU-RSES-Education/EMSC-QuartoBook-Course/issues)
- **Discussions**: [GitHub Discussions](https://github.com/ANU-RSES-Education/EMSC-QuartoBook-Course/discussions)

## 📄 License

MIT License - see [LICENSE](LICENSE) for details.

## 🏛 Acknowledgments

Developed by the [ANU Research School of Earth Sciences](https://earthsciences.anu.edu.au/)
