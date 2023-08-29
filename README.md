# Action-Ahk2Exe
GitHub Action to compile AutoHotKey V2 scripts using Ahk2Exe

Reference to https://github.com/nekocodeX/GitHub-Action-Ahk2Exe/tree/main

# Inputs
|  name    | Type     |Required|Description |
|:-----|:-----|:-----|:-----|
|in|String|True|The path and name of the script to compile|
|out|String |False|The path\name of the output .exe to be created|
|base|Number |False|compile bit number 32|64|

# Example usage
```yml
name: Install ahkv2 on Windows

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: windows-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v2

    - name: Ahk2Exe
      uses: CCCC-L/Action-Ahk2Exe@main
      with:
        in: example.ahk

    - name: Release
      uses: actions/upload-artifact@master
      with:
        name: example
        path: example.exe
```
