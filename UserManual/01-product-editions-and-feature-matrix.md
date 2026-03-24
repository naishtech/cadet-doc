# Product Editions and Feature Matrix

## Editions

- CADET Lite: Free edition focused on Unity build workflows.
- CADET Pro: Paid edition with full publishing and deployment capabilities.

## Feature Matrix

| Feature | Lite | Pro |
|---|---|---|
| Unity Build execution | Yes | Yes |
| Build Queue | Yes | Yes |
| Directory Sync mode | Yes | Yes |
| Git Sync mode | No | Yes |
| Publish to Steam | No | Yes |
| Publish to Epic Games Store | No | Yes |
| macOS notarization workflow | No | Yes |
| Publishing Tools window | No | Yes |
| Steam/Epic/macOS credential wizards | No | Yes |

## Practical Meaning

- <span style="color: #D4AF37;">[Pro]</span> steps require CADET Pro.
- Unmarked steps can be performed in any edition.
- If a <span style="color: #D4AF37;">[Pro]</span> feature is unavailable, CADET will disable that action in the UI.

## Typical Paths

- Lite path: profile setup -> directory sync (optional) -> Unity build.
- Pro path: profile setup -> sync -> Unity build -> publish/notarize as selected.
