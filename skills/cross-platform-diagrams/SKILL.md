---
name: cross-platform-diagrams
description: Create diagrams, flowcharts, and architecture drawings that render correctly on any platform (Confluence, Slack, terminals, etc.). MANDATORY: Read this skill BEFORE creating ANY visual representation (boxes, diagrams, flowcharts, ASCII art, etc.).
---

# Cross-Platform Diagrams

Create ASCII diagrams that work across all platforms (Confluence, Slack, terminals, etc.).

## Core Rules

### 1. Use Basic ASCII Characters Only

| Use | Never Use |
|-----|-----------|
| `+` | `┌` `┐` `└` `┘` `├` `┤` `┬` `┴` `┼` |
| `-` | `─` `═` `—` |
| `|` | `│` `║` |
| `>` `<` `v` `^` | `►` `◄` `▼` `▲` `→` `←` `↓` `↑` |

### 2. Use English Text Only

Non-ASCII text (Korean, Chinese, Japanese, etc.) breaks alignment in most platforms.

## Character Reference

| Element | Character |
|---------|-----------|
| Corners | `+` |
| Horizontal lines | `-` |
| Vertical lines | `|` |
| Right arrow | `>` or `-->` |
| Left arrow | `<` or `<--` |
| Down arrow | `v` |
| Up arrow | `^` |
| Bidirectional | `<-->` |

## Examples

### Box Structure

```
+-------------------+
|  Box with title   |
+-------------------+
|  Content here     |
+-------------------+
```

### Flowchart

```
+----------+     +----------+     +----------+
|  Start   | --> | Process  | --> |   End    |
+----------+     +----------+     +----------+
                      |
                      v
                 +----------+
                 |  Error   |
                 | Handler  |
                 +----------+
```

### Nested Architecture

```
+-----------------------------------------------------------+
|                    Container                              |
|  +-----------------------------------------------------+  |
|  |              Service                                |  |
|  |  +-----------+    +------------------------+        |  |
|  |  | Module A  |    | Module B               |        |  |
|  |  |           |<-->| - Feature 1            |        |  |
|  |  +-----------+    +------------------------+        |  |
|  +-----------------------------------------------------+  |
+-----------------------------------------------------------+
```

### Table

```
+--------+--------+--------+
| Col A  | Col B  | Col C  |
+--------+--------+--------+
| Data 1 | Data 2 | Data 3 |
| Data 4 | Data 5 | Data 6 |
+--------+--------+--------+
```

### System Diagram

```
+-----------------+       +-----------------+
|    Frontend     |       |    Backend      |
|  +----------+   |       |  +----------+   |
|  |   React  |   | <---> |  |   API    |   |
|  +----------+   |       |  +----------+   |
+-----------------+       |       |         |
                          |       v         |
                          |  +----------+   |
                          |  |    DB    |   |
                          |  +----------+   |
                          +-----------------+
```
