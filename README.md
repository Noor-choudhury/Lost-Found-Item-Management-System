# Lost & Found Item Management System

A complete web-based Lost & Found system built with PHP, MySQL, HTML, CSS, and Bootstrap. This system allows users to report lost and found items, search for items, and communicate through comments.

## Features

### Core Functionality
- **Home Page**: Display recent lost and found reports with statistics
- **Lost Items Page**: Browse and filter all lost items
- **Found Items Page**: Browse and filter all found items
- **Search & Filter**: Search by keywords, category, location, and status
- **Report Forms**: Report lost and found items with image upload
- **Item Details**: View full item details with comments system
- **Status Updates**: Mark items as resolved
- **User Authentication**: Registration, login, and session management

### Advanced Features
- **Image Upload**: Support for item photos with file validation
- **Comments System**: Users can communicate about items
- **Responsive Design**: Mobile-friendly interface using Bootstrap
- **Pagination**: Handle large numbers of items efficiently
- **Category Icons**: Visual category indicators
- **Statistics Dashboard**: Overview of system activity

## Technical Stack

- **Backend**: PHP 7.4+ with PDO for database operations
- **Database**: MySQL with proper indexing and relationships
- **Frontend**: HTML5, CSS3, Bootstrap 5.3
- **JavaScript**: Vanilla JS for interactive features
- **Icons**: Font Awesome 6.0
- **Security**: Password hashing, input sanitization, CSRF protection

## Installation

### Prerequisites
- PHP 7.4 or higher
- MySQL 5.7 or higher
- Web server (Apache/Nginx)
- GD extension for image handling

### Setup Steps

1. **Clone/Download the project**
   ```bash
   git clone <repository-url>
   cd lost_found_system
   ```

2. **Database Setup**
   ```bash
   # Create MySQL database
   mysql -u root -p
   CREATE DATABASE lost_found_db;
   
   # Import database structure
   mysql -u root -p lost_found_db < sql/database.sql
   ```

3. **Configure Database Connection**
   Edit `includes/db_connect.php`:
   ```php
   $host = 'localhost';
   $dbname = 'lost_found_db';
   $username = 'your_username';
   $password = 'your_password';
   ```

4. **Set File Permissions**
   ```bash
   chmod 755 assets/uploads/
   chmod 644 *.php
   ```

5. **Start Web Server**
   ```bash
   # Using PHP built-in server (development)
   php -S localhost:8000
   
   # Or configure Apache/Nginx virtual host
   ```

## Database Structure

### Tables

**users**
- User authentication and profile information
- Fields: id, username, email, password, full_name, phone, created_at

**items**
- Lost and found item reports
- Fields: id, user_id, title, description, category, status, date_reported, location, contact_info, image_path, is_resolved, resolved_at, created_at, updated_at

**comments**
- User comments on items
- Fields: id, item_id, user_id, username, message, created_at

## File Structure

```
lost_found_system/
├── assets/
│   ├── css/style.css          # Custom styles
│   ├── js/script.js           # Custom JavaScript
│   └── uploads/               # User uploaded images
├── includes/
│   ├── db_connect.php         # Database connection
│   ├── header.php             # Common header
│   └── footer.php             # Common footer
├── sql/
│   └── database.sql           # Database schema
├── index.php                  # Home page
├── lost_items.php             # Lost items listing
├── found_items.php            # Found items listing
├── search.php                 # Search and filter
├── report_lost.php            # Report lost item form
├── report_found.php           # Report found item form
├── item_details.php           # Item details and comments
├── add_comment.php            # Add comment handler
├── update_status.php          # Update item status
├── register.php               # User registration
├── login.php                  # User login
├── logout.php                 # User logout
└── README.md                  # This file
```

## Usage

### For Users
1. **Register/Login**: Create an account or login
2. **Report Items**: Use forms to report lost or found items
3. **Search**: Find items using search and filter options
4. **Communicate**: Leave comments on item pages
5. **Resolve**: Mark your items as resolved when found

### For Administrators
- Monitor system through database
- Manage user accounts
- Handle reported content
- Backup uploaded images

## Security Features

- **Password Hashing**: bcrypt for secure password storage
- **Input Sanitization**: All user inputs are sanitized
- **File Upload Security**: Validated file types and sizes
- **Session Management**: Secure session handling
- **SQL Injection Protection**: PDO prepared statements

## Customization

### Styling
- Modify `assets/css/style.css` for custom styles
- Change Bootstrap theme by updating CDN links
- Customize color scheme using CSS variables

### Categories
- Add new categories in dropdown options
- Update category icons in `getCategoryIcon()` function
- Modify database enum values as needed

### Features
- Add email notifications for new comments
- Implement admin panel
- Add item location mapping
- Enable social media sharing

## Troubleshooting

### Common Issues

1. **Image Upload Fails**
   - Check `assets/uploads/` permissions
   - Verify PHP `upload_max_filesize` setting
   - Ensure GD extension is installed

2. **Database Connection Error**
   - Verify database credentials
   - Check MySQL service status
   - Confirm database exists

3. **Session Issues**
   - Check PHP session configuration
   - Verify session save path permissions
   - Clear browser cookies

## Demo Data

The system includes sample data:
- Demo users: admin/admin, john_doe/password
- Sample lost and found items
- Test comments

## Contributing

1. Fork the repository
2. Create feature branch
3. Make changes with proper testing
4. Submit pull request with description

## License

This project is open source and available under the MIT License.

## Support

For issues and questions:
- Check troubleshooting section
- Review code comments
- Create GitHub issue
- Contact development team

## Version History

- v1.0.0: Initial release with core functionality
- Features: User auth, item reporting, search, comments
- Responsive design with Bootstrap
- Complete CRUD operations
