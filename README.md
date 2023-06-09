# Tests-As-Docmentation
Practice Exercise 

Tests As Documentation
Imagine explaining this Cake Bar app to someone else. How does it behave? Does it rely on other software? How do you run it on a computer? You could read every line in every file to figure that out. Or you could read the documentation.

Documentation is any content separate from implementation code that explains how it works or how to use it. It may provide more concise summaries and explanation than the implementation code can.

Documentation can come in many forms, including plain text, diagrams…and tests! Tests as documentation provide what many other forms cannot: both human-readable text to describe the application and machine-executable code to confirm the app works as described.

This code block from the Cake Bar app describes and tests the “name” functionality.

it('accepts the customer name', () => {
  const name = 'Hungry Person';
 
  browser.url('/');
  browser.setValue('#name', name);
  browser.click('#submit-order');
  browser.url('/');
 
  assert.include(browser.getText('#deliver-to'), name);
});


You can read the description in plain English terms: it accepts the customer name. You can run the test to confirm the functionality works as described.

Instructions

1.Copy and paste the below code into the test/features/user-visits-index-test.js file. This part of the test explains the functionality in easy-to-read text. When you’re done, click Run.

Paste this test structure at the bottom of the file, near line 91.

describe('to clear an order', () => {
  it('deletes the selected options', () => {
 
  });
});


Checkpoint 2 Passed

2.Copy and paste the body of the test within that block (underneath the line containing it). This part of the test will confirm that the clear order button deletes the selected options. When you’re done, click Run.

      const name = 'Indecisive Person';
      const time = '10:00';
 
      browser.url('/');
      browser.setValue('#name', name);
      browser.selectByVisibleText('#select-pickUp', time)
      browser.click('#submit-order');
      browser.click('#clear-order');
      browser.url('/');
 
      assert.equal(browser.getText('#deliver-to'), '');
      assert.equal(browser.getText('#cake-type'), '');
      assert.equal(browser.getText('#fillings'), '');
      assert.equal(browser.getText('#size'), '');
      assert.equal(browser.getText('#pickUp'), '');
      
Checkpoint 3 Passed

3.Run the test suite. You should see the new test fail. By running the suite you’ve confirmed that the application does not behave as expected!

Checkpoint 4 Passed


4.Test this manually. Run npm start in the terminal, reload the page, and see that the clear order button doesn’t exist yet!

Source of exercise: Codecademy Pro
