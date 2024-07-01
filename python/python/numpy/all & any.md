```python
import numpy as np

a = np.arange(10)
a
-> array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

a < 4
-> array([ True,  True,  True,  True, False, False, False, False, False,
       False])

# any -> 하나라도 조건에 만족한다면 true
np.any(a>5), np.any(a<0)
-> (True, False)

# all -> 모두가 조건에 만족한다면 true
np.all(a>5), np.any(a<0)
-> (False, True)

```