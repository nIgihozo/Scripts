#!/bin/bash
# Define the names of the two submission files
FILE1="submission1.txt"
FILE2="submission2.txt"

# Prompt the user to enter desired directory name
echo "---Submissions Directory Manager ---"
read -p "Please enter the directory name for your submissions: " DIR_NAME

# --- Conditional Logic and Actions ---

# 1. Check if a directory with the given name already exists
if [ -d "$DIR_NAME" ]
then
    echo "Directory '$DIR_NAME' already exists."
    echo "Creating submission files inside the existing directory."

    # Create the two submission files inside the specified directory
    touch "${DIR_NAME}/${FILE1} " "${DIR_NAME}/${FILE2}"

   # Check if files were created successfully
   if [ $? -eq 0 ]
   then
       echo "Files '${FILE1} AND '${FILE2}' have been successfully created in '$DIR_NAME'."
   else
       echo "Error: Failed to create files in '$DIR_NAME'. Please check directory permissions."
       exit 1 # Exit with an error status
   fi # Closes:if [ $? -eq 0 ] (inner if)

# 2. Check if a regular file with the given name already exists (if it's not a directory)
elif [ -f "$DIR_NAME" ]
then
    echo "Error: A regular file name '$DIR_NAME' already exists."
    echo "Cannot create a directory with the same name. Please choose a different name or remove the existing file."
    exit 1 # Exit the script with an error status

# 3. If neither a directory nor a file doesn't exists, create directory
else
    echo "Directory 'DIR_NAME' does not exist. Creating now..."
    # Check if directory was created successfully
    if [ $? -eq 0 ]
    then
        echo "Directory '$DIR_NAME' created successfully."
        echo "Create submission files inside the new directory"

        # Create the two submission files inside the newly created directory
        touch "${DIR_NAME}/${FILE1}" "${DIR_NAME}/${FILE2}"

        # Check if files were created successfully
        if [ $? -eq 0 ]
        then
            echo "Files '${FILE1}' and '${FILE2}' have been successfully created in '$DIR_NAME'."
        else
           echo "Error: Failed to create files in '$DIR_NAME'. Please check directory permissions"
           exit 1 # Exit with an error status
        fi # Closes: if [ $? -eq 0 ] (innermost if)
        else
            echo "Error: Failed to create directory '$DIR_NAME'. Please check the permissions or the path."
            exit 1 # Exit with an error status
        fi # Close: if [ $? -eq 0 ] (outer if within else)
fi # Closes: if [ -d "$DIR_NAME" ] (main if/elif/else block)

echo "--- Script Finished ---"



