# scout << "Enter the directory to change to: ";
    cin >> dirname;

    if (_chdir(dirname.c_str()) == 0) {
        char buffer[FILENAME_MAX];
        _getcwd(buffer, FILENAME_MAX);
        cout << "Current directory changed to: " << buffer << endl;
    } else {
        perror("Error changing directory");
    }
}

int main() {
    int choice;
    while (true) {
        cout << "\nDirectory Management System\n";
        cout << "1. List files in current directory\n";
        cout << "2. Create a new directory\n";
        cout << "3. Change working directory\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch(choice) {
            case 1:
                listFiles();
                break;
            case 2:
                createDirectory();
                break;
            case 3:
                changeDirectory();
                break;
            case 4:
                cout << "Exiting program.\n";
                return 0;
            default:
                cout << "Invalid choice. Please try again.\n";
        }
    }
    return 0;
}
