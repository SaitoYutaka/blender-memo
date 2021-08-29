# blender-memo

## 起動時のカレントディレクトリ

`Python console`画面で以下を入力

```
>>> import os.path
>>> print(os.path.abspath(os.path.dirname(".")))
C:\Program Files\Blender Foundation\Blender 2.93
```

## csv ファイルの読み込み

参考 : https://docs.python.org/3/library/csv.html

以下のようなファイル`sample.csv`を用意。
```
Spam, Spam, Spam, Spam, Spam, Baked Beans
Spam, Lovely Spam, Wonderful Spam
```

Text Editor画面で以下のように入力し、実行。
出力は`System console`に出力される(Window -> Toggle System Consoleで表示)

```py
import bpy
from bpy.types import Operator
from bpy.props import FloatVectorProperty
from bpy_extras.object_utils import AddObjectHelper, object_data_add
from mathutils import Vector


import csv

with open('D:\\blender-python\\sample.csv', newline='') as csvfile:
    spamreader = csv.reader(csvfile, delimiter=' ', quotechar='|')
    for row in spamreader:
        print(', '.join(row))
```
