# SOH Webtools

**A collaborative suite of specialized web utilities for comprehensive world-building, documentation, and systematic knowledge management.**

## Overview

SOH Webtools is an integrated toolkit designed to support serious creative projects requiring rigorous documentation, templating, and interactive visualization. Built around a dark-mode, monospace-first aesthetic, the suite emphasizes modularity, consistency, and streamlined workflows for complex collaborative environments.

Originally developed for managing *The Valley*—a fictional ecosystem with detailed ecological, societal, and geographical layers—the tools are generalized for any project requiring token generation, reference management, templated documentation, and interactive mapping.

## Core Features

### 🎯 **Prompt Indexer** (`Prompt_Indexer v2.html`)
A modernized note-taking and prompt management tool with:
- Block-Inline note formatting for context preservation
- Color-coded action buttons (Green: Format, Amber: Copy, Red: Clear)
- Responsive dark-mode interface optimized for rapid indexing

### 🔑 **Token Tools** (`tokens/`)
Three specialized token generators with cryptographic randomization:

- **Rand5 Generator** — Fast 5-character alphanumeric token generation (Web Crypto API)
- **NID Generator** — Multi-segment Node Identifier creation (Nid1: 6 chars, Nid2/Nid3: 5 chars each) using OGPT-standard alphabet `[A-HJ-NP-Za-km-z2-9]`
- **Connection Builder** — Automated two-way and three-way mesh network statement generation with per-field randomization

### 🗺️ **Interactive Map Viewers** (`viewVM/`, `viewSW/`)

#### Valley Map Viewer v2
- **Dual-layer mapping system**: Ecological base maps (Forests, Waterways, Wetlands, Plains, Hills, Mountains) + Societal overlays (Major Centers, Freeland, Heartlands regions, Cogsway, Mudder's Row, Shielding)
- **Floating draggable reference panels**: Color Key (biome colors), Ecological Key (marker hierarchy), Societal Key (zones/locales/features)
- **Dynamic iframe viewport** for in-panel detail viewing
- **Navigation controls**: Previous/Next cycling through base maps and overlays
- Fully hierarchical marker system: 17+ locales with 30+ features across 8 societal zones

#### Silverwall Map Viewer
Parallel mapping tool for additional geographical regions (under development).

### 📚 **Template Library** (`templates/`, `Template_Viewer v2.html`)
A collapsible accordion-based workbench featuring:
- **Core Templates**: Changelog entries, guided activities, reflection entries, session logs
- **Ecological Templates**: Biome, Flora, Fauna, Mineral entries with standardized schemas
- **Societal Templates**: Character, Locale, and Feature documentation
- **MVD Suite** (Minimum Viable Detail): Primers, Arcana, Inventory systems
- **Pop-out capability** for simultaneous multi-template reference
- **Rapid-access library registry** organized by category

### 📖 **Central Dashboard** (`index.html`)
"Mission Control" navigation hub featuring:
- Dropdown-based tool categorization (Core, Tokens, Mapping, Library)
- Persistent iframe viewport for seamless tool integration
- Animated "Lava Bar" gradient for visual continuity
- Zero variable collision via iframe architecture

---

## Project Structure

```
SOH_Webtools/
├── index.html                         # Central dashboard
├── Prompt_Indexer v2.html             # Prompt management tool
├── logs/
│   ├── Changelog.html                 # Interactive changelog viewer
│   ├── core.txt                       # Development log (core features)
│   ├── tokens.txt                     # Development log (token tools)
│   ├── viewVM.txt                     # Development log (map viewer)
│   └── viewSW.txt                     # Development log (silverwall viewer)
├── tokens/
│   ├── Token_Rand5 v1.html           # Random token generator
│   ├── Token_NID v1.html             # Node ID generator
│   └── Token_Connections v1.html     # Network statement builder
├── templates/
│   ├── Template_Viewer v2.html       # Main workbench
│   ├── Template_Popout.html          # Pop-out window support
│   ├── guided_activity.txt           # Activity template
│   ├── reflection_entry.txt          # Reflection template
│   ├── session_entry.txt             # Session log template
│   ├── biome_entry.txt               # Ecology template
│   ├── fauna_entry.txt               # Wildlife template
│   ├── flora_entry.txt               # Botany template
│   ├── mineral_entry.txt             # Geology template
│   └── [other templates...]          # Additional schemas
└── viewVM/
    ├── ValleyMap_Viewer v2.html      # Valley interactive mapper
    ├── Images/                       # Map layer graphics
    └── Markers/                      # Locale/feature documentation
└── viewSW/
    ├── SilverwallMap_Viewer.html    # Regional mapper
    └── [assets...]
```

---

## Design Philosophy

### **Dark-Mode First**
All tools follow a consistent dark aesthetic:
- Background: `#1a1a1a` (near-black)
- Accent colors: Teal (`#4ecdc4`), Lava Red (`#ff6b6b`), Amber (`#f9d423`)
- Typography: Consolas monospace (code-native feel)

### **Modularity via Iframes**
The dashboard uses iframe-sandboxed tool windows to:
- Prevent variable/namespace collisions
- Enable independent development workflows
- Support persistent state without cross-tool interference

### **Template Standardization**
Every entry type (biome, fauna, character, etc.) follows a structured template with:
- Consistent metadata fields (REQ = Required, OPTION = Optional)
- Symbol-based organization for sorting
- Cross-referencing support for interconnected data

### **Homebrewed, Traceable Development**
This toolkit prioritizes **project-owned implementations** wherever practical. We choose to
build features in-context rather than rely on external dependencies so that:
- The system remains **self-contained and stable**.
- Changes are **traceable through commits**, aligning with the rule: *show your work*.
- Breakages are attributable to **known internal changes**, not upstream adjustments.

All scripts are AI-generated and **traceable back to inclusion**, ensuring each feature has
a clear development path for future contributors to follow.

### **Homebrewed, Traceable Development**
This toolkit prioritizes **project-owned implementations** wherever practical. We choose to
build features in-context rather than rely on external dependencies so that:
- The system remains **self-contained and stable**.
- Changes are **traceable through commits**, aligning with the rule: *show your work*.
- Breakages are attributable to **known internal changes**, not upstream adjustments.

All scripts are AI-generated and **traceable back to inclusion**, ensuring each feature has
a clear development path for future contributors to follow.

---

## Getting Started

### Running Locally
1. **Clone or download** this repository
2. **Open `index.html`** in a modern web browser
3. Navigate via the top dropdown menu:
   - **CORE** → Prompt Indexer, Changelog
   - **TOKENS** → Token generators
   - **MAPPING** → Interactive map viewers (open in new tabs)
   - **LIBRARY** → Template workbench

### Using Individual Tools

#### Token Generators
- Click the **🎲 Dice** button next to any input field for cryptographic randomization
- Copy results to clipboard with the **Copy to Clipboard** button
- Multi-field generation for complex identifiers

#### Map Viewers
1. Select a **Base Map Layer** (ecological layer)
2. Optionally overlay a **Societal Layer** (regional/cultural zones)
3. Toggle floating **Key panels** (Color, Ecological, Societal)
4. Click markers to load detailed information in the right-side iframe viewport
5. Use **Prev/Next** buttons to cycle through layers

#### Template Workbench
1. Expand categories in the left accordion
2. Select a template from the library
3. **Edit** the template content directly in the main textarea
4. **Pop-out** to open in a separate window for reference-side-by-side work
5. **Copy** the entire template to clipboard

---

## Collaborative Workflow

This toolkit is designed for **team-based world-building**:

- **Guided Activities** capture collaborative sessions and methodology
- **Reflection Entries** document learning and decisions
- **Session Logs** track project milestones and credits
- **Template Standardization** ensures consistency across contributors

All documentation includes timestamped entries with contributor credits (e.g., `-JMC-`, `-Gemini-`, `-Claude-`, `-Nio-`, `-Alder-`, etc.).

---

## Technology Stack

- **Frontend**: Vanilla HTML5 + CSS3 + JavaScript (ES6+)
- **Cryptography**: Web Crypto API (CSPRNG-based token generation)
- **Architecture**: iframe-based modular design
- **No external dependencies** — fully self-contained

---

## Recent Updates (v2.0 Milestone)

- ✨ ValleyMap Viewer v2: Complete overhaul with floating key panels and iframe viewport
- 📚 Template Library v2: Collapsible accordion organization with pop-out support
- 🔄 Prompt Indexer v2: Modern UI with block-inline note formatting
- 📋 Comprehensive documentation system with searchable logs

---

## Future Roadmap

- Silverwall Map Viewer feature parity with Valley Viewer
- Search/filter functionality across template library
- Export templates to markdown or structured formats
- Collaborative session management and versioning
- Data persistence via localStorage or IndexedDB

---

## License & Credits

Developed collaboratively by the creative team, with special recognition to:
- **-JMC-** (Project lead, implementation)
- **-Gemini-** (Architecture, UI/UX)
- **-Claude-** (Development support)
- **World-builders & Contributors**: -Alder-, -Nerris-, -Nio-, -Lexi-, -Artie-, -Dex-, and others

---

## Contact & Contributions

For questions, suggestions, or to contribute templates and tools, reach out to the core team.
