# Diario TDD

## Ciclo 1

### Red
- Prueba añadida:

```python
def test_one_feature_is_tiny():
    assert classify_model_size(1) == "tiny"
```
- Técnica de diseño de pruebas empleada:
TDD
- Motivo de elegir este caso:
Está bien
- Fallo observado:
No está contemplado el 1
### Green
- Código mínimo escrito:
```python
return "tiny"
```
- Resultado de las pruebas:
Passed
### Refactor
- Mejora realizada, o motivo por el que no era necesaria:
No era necesaria porque no habían más casos
---


## Ciclo 2

### Red
- Prueba añadida:

```python
def classify_model_size(feature_count: int) -> str:
    if feature_count < 1:
        raise ValueError("feature_count debe ser positivo")
    return "tiny"

```
- Técnica de diseño de pruebas empleada:
TDD
- Motivo de elegir este caso:
Está bien
- Fallo observado:
No está contemplado los numeros menores de 1
### Green
- Código mínimo escrito:
```python
if feature_count < 1:
        raise ValueError("feature_count debe ser positivo")
```
- Resultado de las pruebas:
Passed
### Refactor
- Mejora realizada, o motivo por el que no era necesaria:
No era necesaria porque no habían más casos
---

## Ciclo 3

### Red
- Prueba añadida:

```python
def test_five_features_is_tiny():
    assert classify_model_size(5) == "tiny"

def test_six_features_is_small():
    assert classify_model_size(6) == "small"

```
- Técnica de diseño de pruebas empleada:
TDD
- Motivo de elegir este caso:
Ampliar los rangos de valores
- Fallo observado:
No está contemplado valores diferentes a tiny
### Green
- Código mínimo escrito:
```python
    if feature_count < 1:
        raise ValueError("feature_count debe ser positivo")
    if feature_count <= 5:
        return "tiny"
    return "small"
```
- Resultado de las pruebas:
Passed
### Refactor
- Mejora realizada, o motivo por el que no era necesaria:
No es necesaria porque comprueba bien los rangos
---

## Ciclo 15/16 y 30/31

### Red
- Prueba añadida:

```python
def test_fifteen_features_is_small():
    assert classify_model_size(15) == "small"

def test_sixteen_features_is_medium():
    assert classify_model_size(16) == "medium"

def test_thirty_features_is_medium():
    assert classify_model_size(30) == "medium"

def test_thirty_one_features_is_large():
    assert classify_model_size(31) == "large"

```
- Técnica de diseño de pruebas empleada:
TDD
- Motivo de elegir este caso:
Rangos
- Fallo observado:
No contempla medium y large
### Green
- Código mínimo escrito:
```python
 if feature_count <= 15:
        return "small"
    if feature_count <= 30:
        return "medium"
```
- Resultado de las pruebas:
Passed
### Refactor
- Mejora realizada, o motivo por el que no era necesaria:
No
---
