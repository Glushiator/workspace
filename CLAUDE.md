# Claude Code Environment Knowledge Base

This document contains useful information about working with Claude in this environment.

---

## Environment Details

**OS**: Ubuntu 24.04.3 LTS (Noble Numbat)
**Package Manager**: `apt` / `apt-get`
**User**: `root` (no sudo needed for installations)
**Working Directory**: `/home/user/workspace`

---

## PDF Processing

### Large PDF Problem & Solution

**Issue**: Claude's Read tool can struggle with large PDF files (e.g., academic papers with many pages). Even attempting to read single pages from large PDFs may fail.

**Solution**: Split large PDFs into individual pages FIRST using `pdftk`, then process each page separately.

### pdftk Installation & Usage

`pdftk-java` is available and working in this environment.

**Install:**
```bash
apt update && apt install -y pdftk-java
```

**Common Commands:**

Split PDF into individual pages:
```bash
pdftk large_paper.pdf burst output page_%03d.pdf
# Creates: page_001.pdf, page_002.pdf, page_003.pdf, etc.
```

Extract specific page range:
```bash
pdftk input.pdf cat 1-10 output pages_1-10.pdf
```

Merge multiple PDFs:
```bash
pdftk page_001.pdf page_002.pdf page_003.pdf cat output merged.pdf
```

Merge all PDFs in directory (sorted):
```bash
pdftk *.pdf cat output complete.pdf
```

Get PDF metadata:
```bash
pdftk file.pdf dump_data
```

### Recommended Workflow for Large PDFs

1. Upload large PDF to workspace
2. Ask Claude to split it with pdftk first
3. Process individual pages using Read tool
4. Use sub-agents for comprehensive analysis across all pages

Example:
```bash
# Split academic paper
pdftk paper.pdf burst output page_%03d.pdf

# Then Claude can read each page
# Then use general-purpose or Explore agent to analyze all pages
```

---

## Sub-Agents Available

### general-purpose
- Researching complex questions
- Searching for code
- Multi-step autonomous tasks

### Explore
- Fast codebase exploration
- File pattern matching
- Code keyword searching
- Modes: "quick", "medium", "very thorough"

### Other Agents
- statusline-setup
- output-style-setup

---

## Git Workflow

**Current Branch Naming Convention**: `claude/<descriptive-name>-<session-id>`

### Push Commands
Always use:
```bash
git push -u origin <branch-name>
```

**CRITICAL**: Branch must start with `claude/` and end with matching session ID, otherwise push fails with 403.

### Retry Logic for Network Issues
If push/fetch/pull fails due to network errors, retry up to 4 times with exponential backoff:
- 2s, 4s, 8s, 16s

---

## Repository Purpose

This repository serves as a **scratchpad workspace** for processing files and tasks with Claude.

- Files can be uploaded temporarily for analysis
- Only `CLAUDE.md` persists as knowledge documentation
- Other files are ephemeral and task-specific

---

## Tips & Tricks

### Parallel Tool Calls
Claude can call multiple independent tools in a single response for better performance.

### File Operations
- Use dedicated tools (Read, Write, Edit) instead of bash commands
- Bash is for actual system commands, not file manipulation

### Package Installation
Since running as root, install packages directly:
```bash
apt update
apt install -y <package-name>
```

No sudo needed.

---

## Future Enhancements

Add new sections here as you discover useful patterns, tools, or workflows.
