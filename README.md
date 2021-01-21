# Test Driven Development (TDD)

## The TDD loop: Red, Green, Refactor.
- Write a failing test.
- Write the minimal amount of code for the test to pass.
- Refactor (if needed).

### Advantages

- Gives confidence when refactoring; tests act as a safety harness.

### Tips

- Keep tests small
  - Avoids big slow tests
- Keep tests independent from one another
  - Interdependent tests are brittle and hard to maintain

### Test structure: Given, When, Then

```python
def test_dog_makes_woof_sound():
  # Given
  dog = Dog()
  
  # When
  dog.bark()
  
  # Then
  assertTrue("woof" in dog.sounds())
```
