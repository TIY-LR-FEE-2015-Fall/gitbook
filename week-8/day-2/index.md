# Tuesday December 8

## Ember Testing Day 1

- Handlebars Helpers
  * What are they?
  * What do they do?
  * How do we use them?
  * Unit Tests
    - Pad Zeros
      * Given a number make pad zeroes in front of the value so that 9 turns into "09" but 10 remains "10".
      * Test Cases:
        - padZeros(9) // "09"
        - padZeros(10) // "10"
        - padZeros(100) // "100"
      * Refactor:
        - Make it so that the padZeros function takes an optional second parameter that says how many digits that should be padded to.
        Keep all existing functionality working.
        - Test Cases:
          - padZeros(1, 3) // "001"
          - padZeros(100, 3) // "100"
          - padZeros(10, 5) // "10000"
    - Duplicate Letters
      * Given a string return an array of any repeated characters in the string.
      * Test Cases:
        - duplicateLetters('abcde') // []
        - duplicateLetters('aabbcde') -> // ['a', 'b']
        - duplicateLetters('aabbcde') -> // ['a', 'b']
        - duplicateLetters('aabbcdeB') -> // ['a', 'b']
        - duplicateLetters('indivisibility') -> // ['i']
        - duplicateLetters('Indivisibilities') -> // ['i', 's']
- Ember Computed Properties
  * What are they?
  * What do they do?
  * How do we use them?
  * How do we test them?
  * Unit Tests:
    - Pizza Gluten Tester!
      * Given a Pizza Ember Data model with an array of allergens, decide if the pizza `hasGluten` as a boolean value
      * Test Cases:
        - var p = Pizza.create({allergens: []}); p.get('hasGluten') // false
        - var p = Pizza.create({allergens: ['dairy']}); p.get('hasGluten') // false
        - var p = Pizza.create({allergens: ['wheat']}); p.get('hasGluten') // true
        - var p = Pizza.create({allergens: ['wheat', 'dairy']}); p.get('hasGluten') // true

## Lab

## Deploying Ember Apps

* [surge.sh](http://surge.sh)

* `ember install ember-cli-surge@rtablada/ember-cli-surge#bugfix/surge`
* Change project name in `CNAME` file
* Run `ember surge`

### Videos

* [Introduction to Ember Testing](https://vimeo.com/146960505)
* [Outside In TDD](https://vimeo.com/146953048)
