# function_scope
MDN active learning practive 

    *First, make a local copy of our function-scope.html example. This contains two functions called a() and b(), and three variables — x, y, and z — two of which are defined inside the functions, and one in the global scope. It also contains a third function called output(), which takes a single parameter and outputs it in a paragraph on the page.

    *Open the example up in a browser and in your text editor.

    *Open the JavaScript console in your browser developer tools. In the JavaScript console, enter the following command:
        
        output(x); 
        
        (You should see the value of variable x printed to the browser viewport.)

    *Now try entering the following in your console
        output(y);
        output(z);
    
        Both of these should throw an error into the console along the lines of "ReferenceError: y is not defined". Why is that? Because of function scope — y and z are locked inside the a() and b() functions, so output() can't access them when called from the global scope.

    *However, what about when it's called from inside another function? Try editing a() and b() so they look like this:

        function a() {
            const y = 2;
            output(y);
        }

        function b() {
            const z = 3;
            output(z);
        }

        Save the code and reload it in your browser, then try calling the a() and b() functions from the JavaScript console:

        a();
        b();

        You should see the y and z values printed in the browser viewport. This works fine, as the output() function is being called inside the other functions — in the same scope as the variables it is printing are defined in, in each case. output() itself is available from anywhere, as it is defined in the global scope.

    *Now try updating your code like this:

        function a() {
            const y = 2;
            output(x);
        }

        function b() {
            const z = 3;
            output(x);
        }

    *Save and reload again, and try this again in your JavaScript console:

        a();
        b();

        Both the a() and b() call should print the value of x to the browser viewport. These work fine because even though the output() calls are not in the same scope as x is defined in, x is a global variable so is available inside all code, everywhere.

    *Finally, try updating your code like this:

        function a() {
            const y = 2;
            output(z);
        }

        function b() {
            const z = 3;
            output(y);
        }

    *Save and reload again, and try this again in your JavaScript console:

        a();
        b();


