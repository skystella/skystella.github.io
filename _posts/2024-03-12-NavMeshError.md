---
title: 앱 빌드중 NavMesh오류
author: cotes
date: 2024-03-12 16:00:00 +9
categories: [Summary Note]
tags: [summary note, eror note, error, build error]
pin: false
---

## 앱 빌드중 An asset is marked with HideFlags.DontSave but is included in the build

유니티에서 게임 빌드중에 3개의 오류발생 
1. An asset is marked with HideFlags.DontSave but is included in the build: (파일 경로) Asset name: NavMeshSurface2d Icon (You are probably referencing internal Unity data in your build.) UnityEditor.BuildPlayerWindow:BuildPlayerAndRun ()
2. Assertion failed on expression: 'm_LockCount == 0' UnityEditor.BuildPlayerWindow:BuildPlayerAndRun ()
3. Building - Failed to write file: resources.assets UnityEditor.BuildPlayerWindow:BuildPlayerAndRun ()
파일경로를 바꿔서 해결(글쓴이는 Resource파일에 넣었더니 오류발생함)