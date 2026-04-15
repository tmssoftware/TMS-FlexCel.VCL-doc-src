---
uid: TCollapseChildrenMode
description: TCollapseChildrenMode
---

# TCollapseChildrenMode Enumeration

Determines how the children of the node of an outline will be when the node  is collapsed or expanded\.


## Syntax

**Unit:** [FlexCel.Core](index.md)

## Members

|Name|Value|Description|
|---|---|---|
|DontModify|0|Children nodes will be kept in the state they already were\. If they were collapsed they will still be collapsed after collpasing or expanding the parent\. Same if they were expanded\.<br />|
|Collapsed|1|All children nodes of collapsed parents will be collapsed, and will show collapsed when you expand the parent\.<br />|
|Expanded|2|All children nodes of collapsed parents will be expanded, and will show expanded when you expand the parent\.<br />|


