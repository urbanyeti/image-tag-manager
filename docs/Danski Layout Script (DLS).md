## Overview
- DLS V1 uses YAML syntax.
- Each item in DLS V1 is a UI component with associated properties.
- The `children` attribute is used to specify nested components.
- The `dynamic: true` attribute on a component indicates that multiple instances of this component may be dynamically generated at runtime.
## Example
```dls
App Component:
  Main SplitPane:
    direction: horizontal
    defaultSize: 50%
    children:
      - Image Panel:
          children:
            - Image Container
      - Tags SplitPane:
          direction: vertical
          defaultSize: 33%
          children:
            - Group Tags Panel:
                children:
                  - Read-Only Text Box:
                      id: global-tags
                      wrap: true
                      minLines: 1
                  - Read-Only Text Box:
                      id: local-tags
                      wrap: true
                      minLines: 1
            - File Tags Panel:
                children:
                  - Tag Text Boxes Container:
                      dynamic: true
                      children:
                        - Text Box:
                            id: tag1
                  - Add Button

```
