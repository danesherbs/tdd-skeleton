
## The TDD loop: Red, Green, Refactor.
- Write a failing test.
- Write the minimal amount of code for the test to pass.
- Refactor (if needed).

## Advantages

- Tests give confidence when refactoring since they act as a safety harness.
- Brittle tests are quickly found in the refactoring part of the TDD loop, leading to an overall less brittle test suite.
- Emergent design

## Test structure

### Use the Given-When-Then structure
Improves the readability of test cases, especially when there are many.

❌
```python
def test_dog_makes_woof_sound():
  assertTrue("woof" in Dog().bark().sounds())
```

✅
```python
def test_dog_makes_woof_sound():
  # Given
  dog = Dog()
  
  # When
  dog.bark()
  
  # Then
  assertTrue("woof" in dog.sounds())
```


### Test one behaviour at a time
Allows you to test behaviours independently of one another.

Makes debugging easier when test cases are failing.

❌
```python
def test_dog_makes_sounds():
  # Given
  dog = Dog()
  
  # When
  dog.bark()
  dog.sniff()
  
  # Then
  assertTrue("woof" in dog.sounds())
  assertTrue("sniff" in dog.sounds())
```
  
✅
```python
def test_dog_makes_woof_sound():
  # Given
  dog = Dog()
  
  # When
  dog.bark()
  
  # Then
  assertTrue("woof" in dog.sounds())
  

def test_dog_makes_sniff_sound():
  # Given
  dog = Dog()
  
  # When
  dog.sniff()
  
  # Then
  assertTrue("sniff" in dog.sounds())
```

### Keep tests independent
Independent tests are easier to reason about.

❌
```python

dog = Dog()

def test_dog_makes_woof_sound():
  # When
  dog.bark()
  
  # Then
  assertEqual(dog.sounds(), ["woof"])

def test_dog_makes_sniff_sound():
  # When
  dog.sniff()
  
  # Then
  assertEqual(dog.sounds(), ["sniff"])  # Failure: expected  ["sniff"] but got ["woof", "sniff"]
```
  
✅
```python
def test_dog_makes_woof_sound():
  # Given
  dog = Dog()
  
  # When
  dog.bark()
  
  # Then
  assertEqual(dog.sounds(), ["woof"])
  

def test_dog_makes_sniff_sound():
  # Given
  dog = Dog()
  
  # When
  dog.sniff()
  
  # Then
  assertEqual(dog.sounds(), ["sniff"])
```


