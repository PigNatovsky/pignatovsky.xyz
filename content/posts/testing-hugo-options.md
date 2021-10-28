---
date: 2021-04-26
title: Testing post 
author: PigNatovsky
tags: [hugo]
description: "Just playing with Hugo options"
---

### Source code snippets


Hugo `<code>` wrapper.

{{< code language="bash" title="Example bash script" expand="Show" collapse="Hide" isCollapsed="false">}}
#!/bin/zsh

while ([[ -z $(ip a | grep tun0) ]]); do
	echo "Waiting for tun0 interface ..."
	sleep 1
done

echo "Interface tun0 found!"
echo "Setting up new routes"
sudo ip r del default dev tun0
sudo ip r add 126.0.0.0/8 dev tun0
sudo ip r add 10.0.0.0/8 dev tun0

{{< /code >}}
{{< code language="css" title="CSS snippet" id="1" expand="Show" collapse="Hide" isCollapsed="false" >}}
pre {
  background: #1a1a1d;
  padding: 20px;
  border-radius: 8px;
  font-size: 1rem;
  overflow: auto;

  @media (--phone) {
    white-space: pre-wrap;
    word-wrap: break-word;
  }

  code {
    background: none !important;
    color: #ccc;
    padding: 0;
    font-size: inherit;
  }
}
{{< /code >}}

And now classic MD code wrapper:
```bash

NAPIS="napis"
echo $NAPIS
```


### Integration with [FontAwesome](https://fontawesome.com/)

New partial `font_awesome` for adding glyphs: 
{{< code language="hugo-template" title="Usage of font_awesome partial" expand="Show" collapse="Hide" isCollapsed="false">}}
{{</* font_awesome style="fas" glyph="fa-compact-disc" */>}}
{{< /code >}}

And effect: {{< font_awesome style="fas" glyph="fa-compact-disc" >}}