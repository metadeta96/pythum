# pythum

Simple minimalist quantum computing simalation for python

```python
import pythum
```

## Usage

### Qubit

Class for qubit manipulation and instanciation by notation

```python
from pythum import Qubit

qubit = Qubit()
```

> |0>

#### Public Methods

##### Qubit.from_notation(cls, value: str) -> 'Qubit'

Instanciate a qubit by the formal notation.

The following are possible values:

* "|0>": 0
* "|1>": 1
* "|10>", "|01>": super position

```python
from pythum import Qubit

qubit1 = Qubit.from_notation("|0>")  # 0
qubit2 = Qubit.from_notation("|1>")  # 1
qubit3 = Qubit.from_notation("|10>")  # Super position
```

> |0>
> |1>
> |01>

##### Qubit.from_qubit(cls, qubit: 'Qubit') -> 'Qubit'

Instanciate a copy of another qubit.

```python
from pythum import Qubit

qubit1 = Qubit.from_notation("|1>")  # 1
qubit2 = Qubit.from_qubit(qubit1)  # 1
```

> |1>
> |1>

##### up(self) -> 'self'

Points up the eletron.

The outcome of any measure will always be 1

```python
from pythum import Qubit

qubit = Qubit()  # 0
qubit.up()       # 1
```

> |1>

##### down(self) -> 'self'

Points down the eletron.

The outcome of any measure will always be 0

```python
from pythum import Qubit

qubit = Qubit()  # 0
qubit.up()       # 1
```

> |0>

##### left(self) -> 'self'

Points the eletronto the left.

The outcome of a measure may be 0 or 1

```python
from pythum import Qubit

qubit = Qubit().left()  # Super position
```

> |01>

##### right(self) -> 'self'

Points the eletronto the right.

The outcome of a measure may be 0 or 1

```python
from pythum import Qubit

qubit = Qubit().left()  # Super position
```

> |01>

#### Properties

##### alpha

Alpha probability for mesuring 0.

The returned probability is a number between 0 and 1.

```python
from pythum import Qubit

Qubit().alpha
Qubit().up().alpha
Qubit().left().alpha
Qubit().right().alpha
```

> 1
> 0
> 0.5
> 0.5

##### beta

Beta probability for mesuring 1

The returned probability is a number between 0 and 1.

```python
from pythum import Qubit

Qubit().beta
Qubit().up().beta
Qubit().left().beta
Qubit().right().beta
```

> 0
> 1
> 0.5
> 0.5

### Qublock

#### Public methods

##### __init__(self, value: Union[int, 'Qublock', List[Qubit]])

