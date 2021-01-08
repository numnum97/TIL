``` python
class sklearn.linear_model.LogisticRegression(penalty='l2', dual=False,, tol=0.0001, C=1.0, fit_intercept=True,
intercept_scaling=1, class_weight=None, random_state=None, solver='lbfgs', max_iter=100, multi_class='auto',
verbose=0, warm_start=False, n_jobs=1)
```

[변수]
- penalty: 페널티를 부여할 때 사용할 기준('1l', 'l2')
- dual: Dual Formulation인지 Primal Formulation인지를 결정(True, False)
- tol: 중지 기준에 대한 허용 오차 값
- C: 낮추면 규제 강도가 강해지고, 높이면 규제 강도가 약해짐, 규제 파라미터 람다의 역수
- fit_intercept: 의사 결정 기능에 상수를 추가할 지 여부 결정(True, False)
- intercept_scaling: solver가 'liblinear'이고 fit_intercept가 True일 때 사용 가능
- class_weight: 클래스에 대한 가중치들의 값
- random_state: 데이터 섞을 때 랜덤 생성기의 시드 값
- solver: 최적화에 사용할 알고리즘('newton-cg', 'lbfgs', 'liblinear', 'sag', 'saga')
- max_iter: solver가 수렴하게 만드는 최대 반복 횟수 값
- multi_class: 'auto', 'ovr', 'multinomial'
- verbose:
- warm_start: 이전 호출에 사용했던 solution을 재사용 할지 여부 결정(True, False)
- n_jobs: 병렬처리 시 사용할 CPU 코어의 수

[주의할 점]
1.penalty
- solver 중 'newton-cg', 'sag', 'lbfgs'는 'l2'만 지원, 'saga', 'liblinear'는 모두 지원
2.dual
- Dual Formultaion은 solver를 'liblinear', penalty='l2'로 사용한 경우에만 가능
3.solver
- 작은 데이터셋에선, 'liblinear'가 좋고, 큰 데이터셋에선, 'sag'와 'saga'가 빠르다
- 'liblinear'는 ovr에서만 가능
</br>

[출처: https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)
