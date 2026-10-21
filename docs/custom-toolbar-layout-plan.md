# Custom toolbar layout extension

Goal: allow custom SVG toolbar actions from Shortcuts and ExternalViewers to be positioned among built-in toolbar commands, while preserving existing settings compatibility.

Example (proposed syntax; not yet implemented):

```text
ToolbarCustomLayout = SilentPrint CmdOpenFile SaveAs CmdPrint | PageInfo CmdZoomOut CmdZoomIn
```

Implementation checklist:
- Identify the existing toolbar layout parser and custom command registration.
- Resolve custom action names without collisions with built-in commands.
- Build a single ordered list of toolbar buttons, preserving stable command IDs.
- Update button state, tooltips, layout and visibility handling to use the combined list.
- Keep old configuration behavior when no custom names appear in ToolbarCustomLayout.
- Add tests and verify a Windows build before merging to master.
