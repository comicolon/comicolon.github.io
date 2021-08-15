---
layout : post
title : 한글깨짐 해결
description :
parent : python
has_children: false
nav_order : 100
---

# 한글 깨짐 현상 해결 방법
{: .text-center}

```python
import matplotlib as mpl

# 폰트 변환
# Windows
mpl.rc("font", family='Malgun Gothic')

# MacOS
mpl.rc("font", family='AppleGothic')

# 마이너스 사인 수정
mpl.rc('axes', unicode_minus=False)
```

