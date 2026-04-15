---
uid: TWorkspace.LoadLinkedFile
description: TWorkspace.LoadLinkedFile
---

# TWorkspace.LoadLinkedFile Event

Use this event to load files to recalculate on demand, if you don't know a priori which linked files you need\.
Note that this event will add the new file to the workspace\.
It will only be called once for each file, even if the file is used many times\.


## Syntax

**Unit:** [FlexCel.Core](../index.md)

<pre><code class="lang-delphi hljs">property <a href="../TWorkspace/index.md">TWorkspace</a>.LoadLinkedFile: TLoadLinkedFileEventHandler</code></pre>

## See also

* [TWorkspace](../TWorkspace/index.md)

