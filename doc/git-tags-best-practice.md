# Best Practice: Using Git Tags for VS Code Extensions

Using **Git tags** is an essential best practice to keep your extension versions aligned with the **Visual Studio Code Marketplace**.

---

## 🎯 Why use tags?

Tags allow you to:

- Identify exactly which code corresponds to a published version
- Easily roll back to previous versions
- Keep GitHub and Marketplace versions consistent
- Improve traceability and project organization

Each version published to the Marketplace should have a **corresponding tag** in the repository.

---

## 🏷️ Recommended naming convention

Use **Semantic Versioning** with the `v` prefix:

```text
vMAJOR.MINOR.PATCH
```

Examples:
- `v0.0.1`
- `v1.0.0`
- `v1.2.3`

The tag **must exactly match** the `version` field in `package.json`.

---

## 🧩 When should you create the tag?

The recommended workflow is:

1. Update the `version` field in `package.json`
2. Publish the extension using:
   ```bash
   vsce publish
   ```
3. Create the Git tag after a successful publication

---

## 🛠️ How to create and push a tag

### Create the tag locally
```bash
git tag v0.0.1
```

### Push the tag to the remote repository
```bash
git push origin v0.0.1
```

---

## 🔁 Releasing future versions

For each new release:

```bash
# Update package.json version
vsce publish

git commit -am "Release vX.Y.Z"
git tag vX.Y.Z
git push origin vX.Y.Z
```

---

## ✅ Summary

- Always create a tag for each published version
- Keep the tag version identical to `package.json`
- Create the tag **after** publishing to the Marketplace
- Use the `v` prefix for clarity and consistency

This practice ensures a clean, reliable, and professional project history.
