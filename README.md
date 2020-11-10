# Python-TDD-Test-Task

## Initialising the Test Code

First we need to create a class that will act as the testing environment. To do that we need to inherit from the `unittest.TestCase`. Then we need to make a class variable that will create an instance of the class we will be testing.

```python
class TestCalc(unittest.TestCase):
    tested_class = Calculator()
```

### Creating test cases (methods)

Test methods are similar to regular methods/functions. However, their naming should follow the standard conventions of `test_function_name`. This tells the `unittest` and `pytest` module that this will be a test case method. We then use the `assert` function which will be used to check whether the return value from the called function is equal to expected results.
</br>
In the following example we can see that we checking for equality with `assetEqual` this takes an argument of the function we trying to check and the expected result. In our case we wnat to test the `add()` functino from `Calculator` class which is assigned to the `tested_class` variable. We can call that function and pass arguments to it, and the `assertEqual` will check if the returned value matches with our expected value.

```python
def test_add(self):
    self.assertEqual(self.tested_class.add(2, 4), 6)
```

Another use of assert can be checking for boolean values. To do this we will be using the `assertTrue` function. Unlike `assertEqual`, this function only takes one argument, which is the function we are testing and checks if the return value is `True`. There is also an alternative of `assertFalse` to check the opposite result.

```python
def test_divisible(self):
    self.assertTrue(self.tested_class.divisible(4, 2))
```

## What we testing

The functions in the `Calculator` class need to have a return value for the tests to complete. Depending on the assert function you use you will need to return different values.

Example for `assertEqual`

```python
def add(self, val_1, val_2):
    return val_1 + val_2
```

Example for `assertTrue`

```python
def divisible(self, val_1, val_2):
    return val_1 % val_2 == 0
```
