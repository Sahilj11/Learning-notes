## Use user defined function to get array of value and sort them in ascending order 

Here's an example of how to create a user-defined function in JavaScript to get an array of values from the user and then sort them in ascending order:
![[Pasted image 20230927202318.png]]

![[Pasted image 20230927202337.png]]
After sorting

```html
<!DOCTYPE html>
<html>
<head>
    <title>Array Sorting</title>
</head>
<body>
    <h1>Array Sorting</h1>
    <p>Enter a list of numbers separated by commas:</p>
    <input type="text" id="inputArray" placeholder="e.g., 5, 2, 9, 1, 5, 6">
    <button onclick="sortArray()">Sort Ascending</button>
    <div id="result"></div>

    <script>
        // Function to sort an array in ascending order
        function sortAscending(arr) {
            return arr.sort(function(a, b) {
                return a - b;
            });
        }

        // Function to handle sorting when the button is clicked
        function sortArray() {
            const inputElement = document.getElementById('inputArray');
            const resultElement = document.getElementById('result');
            const inputValues = inputElement.value.split(',').map(Number);

            if (inputValues.length > 0) {
                const sortedArray = sortAscending(inputValues);
                resultElement.textContent = 'Sorted Array: ' + sortedArray.join(', ');
            } else {
                resultElement.textContent = 'Please enter a valid list of numbers.';
            }
        }
    </script>
</body>
</html>
```

In this example, we have a user-defined function called `sortAscending(arr)` that takes an array as an argument and sorts it in ascending order using the `sort()` method with a custom comparison function.

The `sortArray()` function is called when the "Sort Ascending" button is clicked. It retrieves the input values entered by the user, splits them into an array, and then sorts and displays the sorted array in the `result` div.

You can enter a list of numbers separated by commas in the input field, and when you click the button, it will sort them in ascending order and display the result.