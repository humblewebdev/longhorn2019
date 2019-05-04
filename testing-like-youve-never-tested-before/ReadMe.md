# Testing Like You've Never Tested Before: Because You Haven't

> Steve Grunwell

## Automated Testing

- Recudes time + changes of human error
- Easily reproducible
- Gateway to CI/CD

## Test Types

- **Unit**: Test the smallest possible unit of an app
- **Integration**: How individual components work togther
- **End-to-end**: An entire path through an application

## Automation testing pyramid

```
  /   E-2-E   \
 / Integration \
/     Unit      \
```

Higher in pyramid is more expensive and time sucking. Lower has more tests.

## Arrange - Act - Assert

1. **Arange**: Setup the scenario
2. **Act**: Run your code
3. **Assert**: Verify what we wanted to happen did happen

## System Under Test (SUT)

- The system we're currently testing:
    - A single method
    - A class
    - A whole feature

## PHPUnit

### Structure

- **TestSuite**: Collection of test classes
- **TestClass**: Collection of test cases
- **TestMethods**: Collection of AAAs (from above)

A helpful way to run tests in CI/CD pipeline, use `--testdox` flag in the command line.

```./vendor/bin/phpunit --testdox```

## Groups allow granular categorization

```php
/**
* @group API
*/
public function testSomething()
{
    // ...
}
```

We can then run 

```phpunit --group=API```

## Incomplete and Skipped

- `markTestIncomplete()` used for times where you write your tests ahead of time and don't want to run them. Things are still evolving.
- `markTestSkipped()` is generally used during testing to quickly skip something when you don't want to deal with it at the moment.

*Overview of test doubles* (Skipped beccause... well, duh)

