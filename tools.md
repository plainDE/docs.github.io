---
layout: default
title: Installation
nav_order: 5
---


# Tools
## Introduction
This page is dedicated to tools located at ```/usr/share/plainDE/tools/```. Currently there are 2 tools written in Python.

## genconfig.py
This tool is responsible for creating <a href="config"><code>config.json</code></a>. This simple tool is started when plainPanel can't find file located at ```~/.config/plainDE/config.json```. It writes options from dictionary to the json file. 

## update-config.py
This tool updates config when needed. It is ran every time plainPanel starts. First of all, it checks ```configVersion``` entry. If ```configVersion``` does not match version written at ```/usr/share/plainDE/release_data```, it renames your ```config.json``` to ```config.json.sav``` and runs ```genconfig.py``` to create a new config. Then it checks differences between configs. Changes are made when:
<ul>
  <li>A new entry found</li>
  <li>Entry has different type of data (i.e., string->int)</li>
</ul>

When the second case happens, we rewrite this entry completely with new default value.

## Troubleshooting
If the ```config.json``` got broken, you can feel free to delete ```~/.config/plainDE/config.json``` file and start plainPanel again. It will automatically generate new ```config.json```

## Conclusion
Tools described above help you to create & update your ```config.json```.
