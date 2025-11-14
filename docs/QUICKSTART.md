# Quick Start Guide

Get started with TreePlan in 5 minutes!

## Installation (2 minutes)

### Step 1: Download
Download `BYTreePlan.xlam` from the [latest release](https://github.com/smrinalsingh/treeplan/releases)

### Step 2: Install

**On Windows:**
1. Open Excel
2. File → Options → Add-Ins
3. At bottom: Manage "Excel Add-ins" → Go
4. Click Browse → select `BYTreePlan.xlam`
5. Check the box next to "BYTreePlan"

**On macOS:**
1. Open Excel  
2. Tools → Excel Add-ins
3. Browse → select `BYTreePlan.xlam`
4. Check the box next to "BYTreePlan"

### Step 3: Enable Macros
When prompted, click "Enable Content" or "Enable Macros"

## Your First Tree (3 minutes)

### Create a Tree
1. Look for the **Tree Plan** tab in Excel ribbon
2. Click **New** → **With 3 Branches**
3. A decision tree appears! 🎉

### Understanding Nodes

Your tree has three types of nodes:

- **Square (Decision)**: You control the choice
- **Circle (Event)**: Random/chance events  
- **Triangle (Terminal)**: End points with outcomes

### Make Changes

**Change a Node Type:**
1. Click any terminal node (triangle)
2. In Tree Plan ribbon: **Change To Decision** → **With 2 Branches**
3. The terminal becomes a decision with 2 new branches!

**Add More Branches:**
1. Click a decision or event node
2. Click **Add Branch**
3. Repeat as needed (up to 5 branches supported well)

**Remove a Branch:**
1. Click any non-root node
2. Click **Remove Branch**
3. That branch disappears

### Copy Parts of Your Tree

**Copy a Subtree:**
1. Click the node where the subtree starts
2. Click **Copy Subtree**
3. Click where you want to paste
4. Click **Paste Subtree**

Great for repeating patterns!

### Configure Options

Click **Options** to:
- Choose from 3 visual themes
- Adjust spacing and sizing
- Customize appearance

## Common Tasks

### Inserting Nodes Mid-Branch

Want to add a decision in the middle of a branch?

1. Click any node (not the root)
2. Click **Insert Decision** or **Insert Event**
3. A new node appears between parent and selected node

### Resetting

Made a mess? Click **Reset** to start over (after confirming)

## Tips & Tricks

💡 **Select carefully**: Click the exact cell that represents a node

💡 **Work left to right**: Build your tree from left (root) to right (terminals)

💡 **Use Copy/Paste**: For repeating structures, copy subtrees

💡 **Name your branches**: Add labels to decision/event branches

💡 **Add probabilities**: For event nodes, add probabilities to branches

💡 **Add values**: For terminals, add outcome values

## Keyboard Navigation

In Office 2010+:
- Press **Alt** to see key tips
- **Alt, T, P** opens Tree Plan tab (varies by language)

## Next Steps

📖 **Learn more**: See [full README](../README.md) for detailed features

🛠️ **Troubleshooting**: Check [Compatibility Guide](docs/COMPATIBILITY.md)

💻 **Contribute**: Read [Contributing Guide](../CONTRIBUTING.md)

🐛 **Found a bug?**: [Report it on GitHub](https://github.com/smrinalsingh/treeplan/issues)

## Example Tree

Here's what you can build:

```
Start → Decision (Invest?)
        ├─ Yes → Event (Success?)
        │        ├─ High (70%) → $100,000
        │        ├─ Med (20%) → $50,000  
        │        └─ Low (10%) → $10,000
        └─ No → $0
```

## Common Questions

**Q: Can I use this for work?**  
A: Yes! MIT license means free for commercial use.

**Q: Does it work on Mac?**  
A: Yes! Fully compatible with Excel for Mac 2016+.

**Q: Can I customize the appearance?**  
A: Yes, click Options to choose themes and adjust spacing.

**Q: Where's my tree saved?**  
A: In your Excel workbook, like any other data.

**Q: Can I share my tree?**  
A: Yes, just share the Excel file. Others need the add-in installed to edit.

**Q: Is there a limit to tree size?**  
A: Not really, but very large trees (100+ nodes) may be slow.

---

**Need help?** [Open an issue](https://github.com/smrinalsingh/treeplan/issues) or check the [full documentation](../README.md).

Happy tree building! 🌳
