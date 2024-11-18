def read_and_modify_file():
    # Ask the user for the filename
    filename = input("Enter the name of the file to read: ")

    try:
        # Open the specified file for reading
        with open(filename, "r") as infile:
            content = infile.read()
        
        # Modify the content (e.g., convert to uppercase)
        modified_content = content.upper()

        # Write the modified content to a new file
        new_filename = "modified_" + filename
        with open(new_filename, "w") as outfile:
            outfile.write(modified_content)

        print(f"Modified content has been written to '{new_filename}'")

    except FileNotFoundError:
        print(f"Error: The file '{filename}' was not found.")
    except PermissionError:
        print(f"Error: You don't have permission to read or write to '{filename}'.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Run the function
read_and_modify_file()
