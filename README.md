# ASSIGNMENT-6
def modify_file():
    try:
        # Ask the user for the file to read from
        source_file = input("Enter the name of the file to read from: ")

        # Try to open and read the file
        with open(source_file, "r") as file:
            content = file.read()

        # Modify the content (example: make it uppercase)
        modified_content = content.upper()

        # Write the modified content to a new file
        new_file = "modified_" + source_file
        with open(new_file, "w") as file:
            file.write(modified_content)

        print(f"✅ Modified content written to '{new_file}' successfully.")

    except FileNotFoundError:
        print(f"❌ Error: File '{source_file}' not found.")
    except PermissionError:
        print(f"❌ Error: Permission denied when accessing '{source_file}'.")
    except Exception as e:
        print(f"❌ An unexpected error occurred: {e}")

# Run the function
modify_file()
