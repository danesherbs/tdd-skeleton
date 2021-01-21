# Test Driven Development (TDD) Exercise

## TDD

### Red, Green, Refactor
- <span style="color:red"><b>FAIL</b></span>. Write a failing test.
- <span style="color:green"><b>PASS</b></span>. Write the minimal amount of code for the test to pass.
- <span style="color:orange"><b>REFACTOR</b></span>. Refactor if needed.

### Advantages

- Gives confidence when refactoring; tests act as a safety harness.

### Given, When, Then

```python
def test_dog_makes_woof_sound():
  # Given
  dog = Dog()
  
  # When
  dog.bark()
  
  # Then
  assertTrue("woof" in dog.sounds())
```
