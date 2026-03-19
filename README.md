# AI Tax Software Monorepo

A monorepo containing both Frappe-based and custom AI Tax implementations.

## Repository Structure

```
AITaxSoftware/
├── Custom/              # Custom AI Tax Engine (FastAPI + React) [submodule]
│   └── github.com/djhome50/ai-tax-custom
├── FrappeBased/         # Frappe Framework Implementation
│   ├── frappe/          # Frappe Framework [submodule]
│   │   └── github.com/djhome50/frappe (upstream: frappe/frappe)
│   ├── erpnext/         # ERPNext [submodule]
│   │   └── github.com/djhome50/erpnext (upstream: frappe/erpnext)
│   └── ai_tax/          # AI Tax Frappe App [submodule]
│       └── github.com/djhome50/ai_tax
└── ChatGPT-AI_Tax_System_Design.md  # System design document
```

## Submodules

All submodules point to forks under `djhome50` on GitHub, with upstream remotes pointing to original repos:

| Submodule | Fork | Upstream |
|-----------|------|----------|
| `FrappeBased/frappe` | djhome50/frappe | frappe/frappe |
| `FrappeBased/erpnext` | djhome50/erpnext | frappe/erpnext |
| `FrappeBased/ai_tax` | djhome50/ai_tax | (original) |
| `Custom` | djhome50/ai-tax-custom | (original) |

## Quick Start

### Clone with Submodules

```bash
# Clone with all submodules
git clone --recursive https://github.com/djhome50/ai-tax-monorepo.git

# Or clone first, then init submodules
git clone https://github.com/djhome50/ai-tax-monorepo.git
git submodule update --init --recursive
```

### Update Submodules from Upstream

```bash
# Update frappe from upstream
cd FrappeBased/frappe
git fetch upstream
git merge upstream/version-15  # or your target branch
git push origin version-15

# Update erpnext from upstream
cd ../erpnext
git fetch upstream
git merge upstream/version-15
git push origin version-15
```

### Working with Submodules

```bash
# Pull latest changes for all submodules
git submodule update --remote

# Check submodule status
git submodule status

# Make changes in a submodule
cd FrappeBased/ai_tax
# ... make changes ...
git add .
git commit -m "Your changes"
git push origin main

# Update parent repo to point to new commit
cd ../..
git add FrappeBased/ai_tax
git commit -m "Update ai_tax submodule"
git push
```

## Development

### Custom (FastAPI + React)

See [Custom/README.md](Custom/README.md) for details.

```bash
cd Custom
docker-compose up -d
```

### Frappe-Based

See [FrappeBased/ai_tax/README.md](FrappeBased/ai_tax/README.md) for details.

```bash
cd FrappeBased
bench start
```

## GitHub Repositories

- **Monorepo**: (create this repo to track submodule versions)
- **Custom Engine**: https://github.com/djhome50/ai-tax-custom
- **AI Tax Frappe App**: https://github.com/djhome50/ai_tax
- **Frappe Fork**: https://github.com/djhome50/frappe
- **ERPNext Fork**: https://github.com/djhome50/erpnext
