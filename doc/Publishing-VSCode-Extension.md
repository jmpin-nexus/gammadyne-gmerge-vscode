# Publishing a VS Code Extension (Step-by-Step Guide)

This document explains **how to publish a Visual Studio Code extension** to the VS Code Marketplace, including common pitfalls and how to avoid them.

---

## 1. Prerequisites

### 1.1 Required Accounts

You **must** have:

- A **Microsoft account**
- An **Azure DevOps organization**
- A **VS Code Marketplace Publisher**

> ⚠️ GitHub accounts and GitHub tokens **are not used** for publishing VS Code extensions.

---

## 2. Create an Azure DevOps Organization

1. Go to:
   https://dev.azure.com

2. Sign in with your Microsoft account

3. If prompted, **create a new organization**
   - Organization name: any valid name (e.g. `nexusbr-dev`)
   - No credit card is required for publishing extensions

> ⚠️ Azure DevOps may show billing pages — these are **not required** for free extensions.

---

## 3. Create a VS Code Marketplace Publisher

1. Go to:
   https://marketplace.visualstudio.com/manage/publishers/

2. Click **Create Publisher**

3. Choose:
   - **Publisher ID** (example: `nexusbr`)
   - Display name
   - Contact email

4. Save the publisher

> The **Publisher ID** will be used later in `package.json`.

---

## 4. Install VSCE (VS Code Extension CLI)

Install the official publishing tool:

```bash
npm install -g @vscode/vsce
```

Verify installation:

```bash
vsce --version
```

---

## 5. Prepare Your Extension Project

### 5.1 Required Files

Your project must contain at least:

```
package.json
README.md
LICENSE.txt
```

> Publishing will warn or fail if LICENSE is missing.

---

### 5.2 package.json (Minimal Example)

```json
{
  "name": "gammadyne-gmerge",
  "displayName": "Gammadyne G-Merge Script",
  "description": "Syntax highlighting and snippets for Gammadyne Mailer (G-Merge) scripts.",
  "version": "0.0.1",
  "publisher": "nexusbr",
  "engines": {
    "vscode": "^1.80.0"
  },
  "categories": ["Programming Languages"],
  "icon": "images/icon.png"
}
```

> ⚠️ The `publisher` **must match exactly** the Marketplace Publisher ID.

---

## 6. Add an Extension Icon (Required)

### Recommended icon specs:
- **Size:** 128×128 pixels
- **Format:** PNG
- **Path:** `images/icon.png`
- **File size:** < 1 MB (recommended)

---

## 7. Login with VSCE (Important)

You must authenticate using an **Azure DevOps Personal Access Token (PAT)**.

### 7.1 Create a PAT

1. Go to:
   https://dev.azure.com

2. Click your profile → **Personal Access Tokens**

3. Create a new token with:
   - Scope: **Marketplace**
   - Access: **Full access**
   - Expiration: your choice

4. Copy the token

---

### 7.2 Login via CLI

```bash
vsce login <publisher-id>
```

Example:

```bash
vsce login nexusbr
```

Paste the **Azure DevOps PAT** (not GitHub token).

✅ Success message:
```
The Personal Access Token verification succeeded
```

---

## 8. Package the Extension (Optional but Recommended)

Before publishing, test packaging:

```bash
vsce package
```

This generates a `.vsix` file and shows included files.

> Useful to catch missing icons, files, or configuration issues.

---

## 9. Publish the Extension

To publish:

```bash
vsce publish
```

If successful, you will see:

```
Published <publisher>.<extension-name> v0.0.1
```

The Marketplace URL will be shown.

---

## 10. Common Errors & Solutions

### ❌ TF400813: Not authorized

**Cause:**
- Using GitHub token
- Wrong publisher name
- Token without Marketplace scope

**Fix:**
- Use Azure DevOps PAT
- Ensure publisher exists
- Login using correct publisher ID

---

### ❌ Icon not found

**Cause:**
- Wrong icon path
- Missing file

**Fix:**
- Ensure icon exists at the path declared in `package.json`

---

### ❌ Credit Card Requested

**Clarification:**
- Publishing **free extensions does NOT require payment**
- Azure billing prompts can be ignored

---

## 11. Updating an Existing Extension

1. Increment version in `package.json`
2. Run:

```bash
vsce publish
```

Marketplace updates automatically.

---

## 12. Useful Links

- VS Code Marketplace:
  https://marketplace.visualstudio.com/

- Manage publishers:
  https://marketplace.visualstudio.com/manage/publishers/

- VSCE documentation:
  https://code.visualstudio.com/api/working-with-extensions/publishing-extension

---

## 13. Final Notes

- Publishing uses **Azure DevOps**, not GitHub
- Tokens are **Azure DevOps PATs**
- Publisher name must match exactly
- Free extensions are fully supported

---

✅ **You are now fully equipped to publish VS Code extensions.**
