1. np.where(a>0, 3, 2)
	1. a>0 조건문이 들어가서 true이면 3, false이면 2가 출력되는 코드
2. np.where(a>5)
	1. a>5 조건에 true인 값을 index를 반환

1. np.isnan(np.array([1, np.NaN, np.Inf], float))
	1. not a number로 메모리에 값이 존재하지 않는 경우
	2. 출력값: array([False, True, False, dtype=bool])
2. np.isfinite(np.array([1, np.NaN, np.Inf], float))
	1. is finite number 한정되지 않은 값.
	2. 출력값: array([True, False, False, dtype=bool])