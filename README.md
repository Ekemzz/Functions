# Functions
Bash functions are reusable blocks of commands within a Bash script or shell environment. They are used to encapsulate a specific task, improve code readability, and avoid repetition.

Defining a Function:

There are two common ways to define a function in Bash: Using the function keyword.
Code

    function function_name {
        # Commands to be executed
    }


---------------------------------------------------------------------------------------
Without the function keyword.
Code

    function_name() {
        # Commands to be executed
    }
or 
 function_name() {" # Function body
 You can place any commands or logic here"
 }

-------------------------------------------------------------------------------------------    
Calling a Function:
To execute the commands within a function, you simply call it by its name:

Code
function_name

**Passing Arguments to Functions:
Arguments can be passed to functions and accessed within the function using positional parameters: $1, $2, etc., where $1 is the first argument, $2 is the second, and so on. $@ refers to all arguments, and $# refers to the number of arguments.

In this project we would be creating several functions. 
1. A function that checks if a script has an argument.

#!/bin/bash

# Checking the number of arguments
if [ "$#" -ne 0 ]; then
    echo "Usage: $0 <environment>"
    exit 1
fi

# Accessing the first argument
ENVIRONMENT=$1

# Acting based on the argument value
if [ "$ENVIRONMENT" == "local" ]; then
  echo "Running script for Local Environment..."
elif [ "$ENVIRONMENT" == "testing" ]; then
  echo "Running script for Testing Environment..."
elif [ "$ENVIRONMENT" == "production" ]; then
  echo "Running script for Production Environment..."
else
  echo "Invalid environment specified. Please use 'local', 'testing', or 'production'."
  exit 2
fi

--------------------------------------------------------------------------------------------------
In order for it to be a function,

#!/bin/bash

check_num_of_args() { Checking the number of arguments
if [ $# -ne 0 ]; then
echo "Usage: $0 <environment>"
exit 1
fi
}

# Accessing the first argument
ENVIRONMENT=$1

# Acting based on the argument value
if [ "$ENVIRONMENT" == "local" ]; then
  echo "Running script for Local Environment..."
elif [ "$ENVIRONMENT" == "testing" ]; then
  echo "Running script for Testing Environment..."
elif [ "$ENVIRONMENT" == "production" ]; then
  echo "Running script for Production Environment..."
else
  echo "Invalid environment specified. Please use 'local', 'testing', or 'production'."
  exit 2
fi

