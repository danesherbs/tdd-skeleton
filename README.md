
## The TDD loop: Red, Green, Refactor.
- Write a failing test.
- Write the minimal amount of code for the test to pass.
- Refactor (if needed).

## Advantages

- Gives confidence when refactoring; tests act as a safety harness.

## Test structure

### Given, When, Then
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


### Keep tests small
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

### Other tips
- Keep tests independent from one another (interdependent tests are brittle and hard to maintain)
