---
title: Automation Tools - File & Folder Management Automation
version: 6.0.0
owner: Administration Department
status: Active
last_updated: '2025-12-09'
---

# Automation Tools

Python automation tools for tax engagement document management, from client folder creation to mail merge, file distribution, and inventory tracking.

## 📁 Tool Structure

```
automation-tools/
├── 1-folder-creation/     # Create client folders
├── 2-mail-merge/          # Generate engagement letters
├── 3-file-movement/       # Move & organize files
├── 4-folder-inventory/    # Inventory & analysis
└── 5-utilities/           # Utility tools
```

## 🚀 Workflow

```
1. Prepare Excel list → 2. Create folders → 3. Mail merge → 
4. Move files → 5. Inventory & archive
```

---

## 1️⃣ Folder Creation

### 📂 `1-folder-creation/`

Automatically create client folders from Excel list.

**Scripts:**
- `create-individual.py` - Create Individual client folders (JAL)
- `create-both.py` - Create both Individual & Business folders

**Folder naming format:**
- Individual: `2025 - JAL - [Tax Payer].[Client ID.Sub ID]`
- Business: `2025 - EL - [Business Name].[Client ID.Sub ID]`

**Usage:**
```powershell
cd automation-tools/1-folder-creation
# Edit config in .py file
python create-individual.py
```

**Details:** [1-folder-creation/README.md](1-folder-creation/README.md)

---

## 2️⃣ Mail Merge

### 📧 `2-mail-merge/`

Generate personalized engagement letters for clients.

**Scripts:**
- `merge-business.py` - For Business clients
- `merge-individual.py` - For Individual clients (auto-selects template with/without spouse)

**Output:**
- Business: `2025 - EL - [Business Name].[Client ID].docx`
- Individual: `2025 - JAL - [Tax Payer].[Client ID].docx`

**Usage:**
```powershell
cd automation-tools/2-mail-merge
# Edit config-business.ini or config-individual.ini
python merge-business.py
# or
python merge-individual.py
```

**Details:** [2-mail-merge/README.md](2-mail-merge/README.md)

---

## 3️⃣ File Movement

### 🔄 `3-file-movement/`

Move files/folders to correct client directories.

**Scripts:**
- `move-files.py` - Move individual files (.docx, .pdf)
- `move-folders.py` - Move folders based on Excel list
- `move-smart.py` - Move from multiple sources with auto-classification
- `reorganize-client-folders.py` - Reorganize folder structure (archive old years)

**Usage:**
```powershell
cd automation-tools/3-file-movement
python move-files.py
# or
python move-smart.py
```

**Details:** [3-file-movement/README.md](3-file-movement/README.md)

---

## 4️⃣ Folder Inventory

### 📊 `4-folder-inventory/`

Inventory and analyze folder structures.

**Scripts:**
- `inventory.py` - Generate comprehensive inventory (tree, CSV, JSON, Excel)
- `check-tax-2025-folders.py` - Check if clients have Tax\2025 folder
- `scan-biz-sharefile-status.py` - Scan business clients on ShareFile, verify Tax Template

**Usage:**
```powershell
cd automation-tools/4-folder-inventory
python inventory.py
# or
python check-tax-2025-folders.py
# or
python scan-biz-sharefile-status.py
```

**Details:** [4-folder-inventory/README.md](4-folder-inventory/README.md)

---

## 5️⃣ Utilities

### 🛠️ `5-utilities/`

Standalone utility tools for special tasks.

**Scripts:**
- `compare-and-copy.py` - Compare 2 folders and copy unique files
- `create-with-csv.py` - Create folders from CSV and update CSV with paths
- `tax-folder-organizer.py` - Automatically organize tax files into proper subfolders

**Usage:**
```powershell
cd automation-tools/5-utilities
python compare-and-copy.py
```

**Details:** [5-utilities/README.md](5-utilities/README.md)

---

## 📋 Requirements & Installation

### Python Version
Python 3.7 or higher

### Install Libraries

```powershell
# Install all required libraries
pip install python-docx pandas openpyxl
```

### Standard Libraries (no installation needed)
Most scripts use Python standard libraries: `os`, `csv`, `re`, `shutil`, `datetime`, `json`

---

## ⚙️ Best Practices

1. **Use Absolute Paths** - Always use full paths with `r` prefix:
   ```python
   base_dir = r"C:\Full\Path\To\Directory"
   ```

2. **Test First** - Test on small data before running on production

3. **Backup** - Always backup data before running bulk operations

4. **Review Logs** - Check log files after each operation

5. **Consistent Naming** - Use standard Client ID format: `CLIENTID.SUBID`

---

## 📝 Standard Naming Format

### Folders:
- Individual: `2025 - JAL - [Tax Payer].[Client ID.Sub ID]`
- Business: `2025 - EL - [Business Name].[Client ID.Sub ID]`

### Documents:
- Individual: `2025 - JAL - [Tax Payer].[Client ID.Sub ID].docx`
- Business: `2025 - EL - [Business Name].[Client ID.Sub ID].docx`

### Client ID Format:
- Standard: `CLIENTID.SUBID` (e.g., `SMITH.01`, `ABC.02`)

---

## 🔧 Troubleshooting

**Python not found**
```powershell
python --version
# If not found, install from python.org
```

**Module not found**
```powershell
pip install python-docx pandas openpyxl
```

**Permission denied**
- Run PowerShell as Administrator
- Close files in Excel/Word before running scripts

**Wrong folders/files moved**
- Check Client ID format
- Review config paths in script

---

## 📞 Support

**Detailed documentation:**
- [1-folder-creation/README.md](1-folder-creation/README.md)
- [2-mail-merge/README.md](2-mail-merge/README.md)
- [3-file-movement/README.md](3-file-movement/README.md)
- [4-folder-inventory/README.md](4-folder-inventory/README.md)
- [5-utilities/README.md](5-utilities/README.md)

---

**Repository:** CM-ShareFile/automation-tools  
**Maintained by:** Administration Department  
**Last Updated:** December 9, 2025
