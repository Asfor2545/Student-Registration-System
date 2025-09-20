# Student Registration System

A comprehensive GUI-based student registration system built with Python Tkinter that allows educational institutions to manage student records efficiently using Excel file storage.

## Features

- **Student Registration**: Register new students with complete details
- **Search Functionality**: Search for existing student records by registration number
- **Update Records**: Modify existing student information
- **Image Management**: Upload and store student profile pictures
- **Data Persistence**: Store student data in Excel format (.xlsx)
- **User-friendly Interface**: Clean and intuitive GUI design

## Requirements

### System Requirements
- Python 3.7 or higher
- Operating System: Windows, macOS, or Linux

### Python Dependencies
```
tkinter (usually comes with Python)
Pillow (PIL)
openpyxl
xlrd
pathlib
datetime
os
```

## Installation

1. **Clone or download the repository**
   ```bash
   git clone <repository-url>
   cd student-registration-system
   ```

2. **Install required Python packages**
   ```bash
   pip install Pillow openpyxl xlrd
   ```

3. **Create required directories**
   ```bash
   mkdir "Student Images"
   mkdir "Images"
   ```

4. **Add required image files**
   Place the following images in the `Images` folder:
   - `upload photo.png` - Default placeholder for student photos
   - `search.png` - Search button icon
   - `Layer 4.png` - Update button icon

## Usage

1. **Run the application**
   ```bash
   python Student-Registraion.py
   ```

2. **Register a new student**
   - Fill in all required fields in the Student Details and Parents' Details sections
   - Upload a profile picture (optional)
   - Click "Save" to register the student

3. **Search for a student**
   - Enter the registration number in the search box
   - Click "Search" to retrieve student information

4. **Update student information**
   - First search for the student using their registration number
   - Modify the required fields
   - Click the "Update" button to save changes

5. **Reset the form**
   - Click "Reset" to clear all fields and prepare for new entry

## File Structure

```
student-registration-system/
│
├── Student-Registraion.py    # Main application file
├── README.md                 # This file
├── Student_data.xlsx         # Excel file storing student data (auto-created)
├── Images/                   # Directory for UI images
│   ├── upload photo.png
│   ├── search.png
│   └── Layer 4.png
└── Student Images/           # Directory for student profile pictures
    └── (student photos stored here)
```

## Data Fields

### Student Information
- Registration Number (auto-generated)
- Full Name
- Class (1-12)
- Gender (Male/Female)
- Date of Birth
- Date of Registration (auto-filled with current date)
- Religion
- Skills
- Profile Picture

### Parent Information
- Father's Name
- Father's Occupation
- Mother's Name
- Mother's Occupation

## Excel Data Structure

The application automatically creates `Student_data.xlsx` with the following columns:

| Column | Field | Description |
|--------|-------|-------------|
| A | Registration No. | Unique student identifier |
| B | Name | Student's full name |
| C | Class | Academic class (1-12) |
| D | Gender | Male or Female |
| E | DoB | Date of Birth |
| F | Date of Registration | Registration date |
| G | Religion | Student's religion |
| H | Skill | Special skills/talents |
| I | Father's name | Father's full name |
| J | Mother's name | Mother's full name |
| K | Father's Occupation | Father's job |
| L | Mother's Occupation | Mother's job |

## Features in Detail

### Registration Number Generation
- Automatically generates sequential registration numbers
- Uses the highest existing registration number + 1
- Ensures uniqueness for each student

### Image Handling
- Supports JPG and PNG formats
- Automatically resizes images to 190x190 pixels
- Stores images in the "Student Images" directory with registration number as filename
- Displays default placeholder when no image is uploaded

### Data Validation
- Ensures all mandatory fields are filled before saving
- Validates registration numbers during search operations
- Provides error messages for invalid operations
- Prevents saving incomplete records

### Excel File Management
- Creates Excel file automatically on first run
- Sets up proper column headers
- Handles concurrent read/write operations
- Maintains data integrity

## Error Handling

The application includes comprehensive error handling for:
- Invalid registration numbers during search
- Missing mandatory fields during registration
- File operation errors (Excel file access)
- Image processing errors
- Missing image files

## Troubleshooting

### Common Issues

1. **Excel File Access Error**
   - Close any open Excel applications that might be using `Student_data.xlsx`
   - Ensure the application has write permissions in the directory
   - Check if the file is not corrupted

2. **Image Not Loading**
   - Check if the "Images" directory exists
   - Ensure required image files (`upload photo.png`, `search.png`, `Layer 4.png`) are present
   - Verify file permissions

3. **Student Photo Not Saving**
   - Ensure "Student Images" directory exists
   - Check write permissions for the directory
   - Verify the uploaded image format is supported (JPG/PNG)

4. **Search Not Working**
   - Ensure the registration number exists in the Excel file
   - Check if `Student_data.xlsx` is accessible
   - Verify the registration number is entered as a number

### File Permissions
- Ensure the application directory has read/write permissions
- On Windows, run as administrator if experiencing permission issues
- On macOS/Linux, check directory permissions with `ls -la`

## Technical Details

### Dependencies Explained
- **tkinter**: GUI framework (comes with Python)
- **Pillow (PIL)**: Image processing for photo upload/display
- **openpyxl**: Reading and writing Excel files (.xlsx format)
- **xlrd**: Reading older Excel files (.xls format)
- **pathlib**: File path operations
- **datetime**: Date handling for registration dates
- **os**: Operating system interface for file operations

### Color Scheme
- Background: `#06283D` (Dark blue)
- Frame Background: `#EDEDED` (Light gray)
- Frame Foreground: `#06283D` (Dark blue)

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly with various data inputs
5. Submit a pull request

## Known Limitations

- Single-user application (no concurrent access)
- Excel file must not be open in other applications during use
- Limited to .xlsx and .xls file formats
- No built-in backup mechanism
- Search only works with exact registration numbers

## Future Enhancements

Potential improvements for future versions:
- Multi-user support with database integration
- Advanced search capabilities (search by name, class, etc.)
- Data export/import functionality
- Automatic backup system
- Print functionality for student records
- Bulk operations support

## License

This project is open source and available under the [MIT License](LICENSE).
