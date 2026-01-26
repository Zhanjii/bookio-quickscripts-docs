---
layout: default
title: User Guide
nav_order: 2
description: "How to use BookIO QuickScripts"
---

# Book.io QuickScripts User Guide

## Table of Contents
1. [Getting Started](#getting-started)
2. [User Interface Overview](#user-interface-overview)
3. [Working with Tabs](#working-with-tabs)
4. [File Management Tabs](#file-management-tabs)
5. [Image Processing Tabs](#image-processing-tabs)
6. [Project Management Tabs](#project-management-tabs)
7. [Admin Features](#admin-features)
8. [Settings and Configuration](#settings-and-configuration)
9. [Notifications](#notifications)
10. [Keyboard Shortcuts](#keyboard-shortcuts)
11. [Troubleshooting](#troubleshooting)
12. [Best Practices](#best-practices)

## Getting Started

### System Requirements
- Windows 10/11, macOS 10.14+, or Linux (Ubuntu 20.04+)
- Python 3.8 or higher
- 4GB RAM minimum (8GB recommended)
- 500MB free disk space

### First Launch

1. **Launch the Application**
   ```
   python -m book_io_quickscripts.main
   ```

2. **Select Master Directory**
   - Click the "Select directory" button in the top toolbar
   - Choose your main working directory where projects will be stored
   - This directory will be used as the base for all operations

3. **Initial Configuration**
   - Click the "Settings" button
   - Navigate to the "Directories" tab
   - Configure the following directories:
     - **APPROVAL_DIR**: Where approval files are stored
     - **RENDER_DIR**: Where render files are stored
     - **UPLOAD_DRIVE**: Directory for uploads
     - **BOX_DIR**: Box integration directory

4. **Enable Required Tabs**
   - In Settings → Tabs
   - Check the tabs you want to use
   - Click "Save" to apply changes
   - Tabs will appear/disappear immediately

### Basic Workflow

1. **Select Master Directory**: Choose your working directory
2. **Choose a Tab**: Click on the appropriate tab for your task
3. **Configure Options**: Set any tab-specific settings
4. **Execute Operation**: Click the main action button (usually "Start" or "Process")
5. **Monitor Progress**: Watch the progress bar and status messages
6. **Review Results**: Check the output and any generated reports

## User Interface Overview

### Main Window Components

1. **Title Bar**
   - Application name and version
   - Standard window controls

2. **Directory Selector Bar**
   - Master Directory field and selector
   - Settings button
   - Admin Mode toggle
   - Log viewer button with current log level indicator

3. **Tab Bar**
   - Displays all enabled tabs
   - Click to switch between tabs
   - Tabs are organized in a grid layout

4. **Content Area**
   - Tab description
   - Tab-specific controls and options
   - Progress indicators
   - Results display

### Status Indicators

- **Green**: Operation successful
- **Orange**: Warning or requires attention
- **Red**: Error occurred
- **Blue**: Information or processing

## Working with Tabs

### Tab Categories

Tabs are organized into functional categories:

1. **File Management**: Count, File Renamer, Missing Covers
2. **Image Processing**: Image Sorter, Dimension Audit, Format & Download
3. **Project Management**: New Project, Zip Creator, Change Request
4. **Content Creation**: Base Generator, Generate Prompts, Multi Prompt
5. **Utilities**: Diagnostics, Billy, Scene Ingest

### Common Tab Features

Most tabs share these common elements:

- **Description Area**: Explains what the tab does
- **Start/Process Button**: Initiates the main operation
- **Progress Bar**: Shows operation progress
- **Cancel Button**: Stops the current operation
- **Results Display**: Shows operation outcomes

## File Management Tabs

### Count Tab

**Purpose**: Count and analyze files in your project structure

**How to Use**:
1. Ensure master directory is selected
2. Click "Start"
3. Review the file count report

**Output**: 
- Total file count by type
- Breakdown by directory
- File size statistics

### File Renamer Tab

**Purpose**: Batch rename files based on patterns

**How to Use**:
1. Select the target directory
2. Choose naming pattern:
   - Prefix: Add text before filename
   - Suffix: Add text after filename
   - Replace: Replace text in filenames
   - Sequential: Number files sequentially
3. Preview changes before applying
4. Click "Rename Files"

**Features**:
- Undo last rename operation
- Case sensitivity options
- Regular expression support

### Missing Covers Tab

**Purpose**: Find projects missing cover images

**How to Use**:
1. Click "Find Missing Covers"
2. Review the list of projects without covers
3. Optional: Generate placeholder images
4. Export report as CSV

**Output**:
- List of projects missing covers
- Paths to incomplete projects
- Summary statistics

## Image Processing Tabs

### Image Sorter Tab

**Purpose**: Organize images by blockchain and book type

**How to Use**:
1. Select source directory containing images
2. Choose sorting criteria:
   - By blockchain code
   - By book type
   - By dimensions
3. Select destination structure
4. Click "Sort Images"

**Features**:
- Automatic blockchain detection from filenames
- Duplicate handling options
- Dry run mode for preview

### Dimension Audit Tab

**Purpose**: Validate image dimensions against standards

**How to Use**:
1. Select directory to audit
2. Choose dimension requirements:
   - Book.io standard dimensions
   - Custom dimension sets
3. Click "Start Audit"
4. Review non-compliant images

**Output**:
- List of images with incorrect dimensions
- Actual vs expected dimensions
- Batch resize options

### Format and Download Images Tab (Admin Only)

**Purpose**: Convert and optimize images for different uses

**How to Use**:
1. Select source images
2. Choose output format:
   - JPEG (quality slider)
   - PNG (compression level)
   - WebP (quality/lossless)
3. Set output directory
4. Configure optimization settings
5. Click "Process Images"

**Advanced Options**:
- Batch watermarking
- Metadata preservation
- Color profile conversion

## Project Management Tabs

### New Project Tab (Admin Only)

**Purpose**: Create standardized project folder structures

**How to Use**:
1. Enter project details:
   - Book name
   - Author (optional)
   - Project type
2. Select blockchains
3. Choose folder template
4. Click "Create Project"

**Created Structure**:
```
MM.DD.YYYY_BOOK_NAME/
├── 01_ADA_APPROVAL/
│   ├── 01_AFTER EFFECTS/
│   └── 02_MASTERS/
├── 02_ADA_RENDER/
│   ├── 01_ADA_bot_titles/
│   ├── 02_ADA_top_titles/
│   └── ...
└── [Additional blockchain folders]
```

### Zip Creator Tab

**Purpose**: Create organized ZIP archives of projects

**How to Use**:
1. Select project folder
2. Choose compression settings:
   - Compression level (0-9)
   - Split size (if needed)
3. Select what to include:
   - All files
   - Specific file types
   - Exclude patterns
4. Click "Create ZIP"

**Features**:
- Progress indication for large archives
- Automatic naming based on project
- Verification after creation

### Change Request Tab

**Purpose**: Manage and track change requests

**How to Use**:
1. Create new request:
   - Request title
   - Description
   - Priority level
2. Attach relevant files
3. Assign to blockchain/project
4. Track status updates

**Workflow States**:
- New → In Progress → Review → Complete
- Can add notes at each stage
- Email notifications optional

## Admin Features

### Enabling Admin Mode

1. **First Time Setup**:
   - Click "Enable Admin Mode" button
   - Enter default password: `book.io_admin`
   - Recommend changing password immediately

2. **Admin Authentication**:
   - Password protected access
   - Session persists until disabled
   - Access to additional tabs and features

### Admin-Only Tabs

**Book Ingest Local**
- Import books from local sources
- Batch processing capabilities
- Advanced metadata editing

**Diagnostics**
- System performance metrics
- Configuration validation
- Debug logging controls
- Error report generation

**Format and Download Images**
- Advanced image processing
- Batch operations
- Format conversion tools

**New Project**
- Create complex project structures
- Template management
- Bulk project creation

### Admin Settings

**Access via Settings → Admin tab**:

1. **Change Admin Password**:
   - Enter current password
   - Enter new password (8+ characters)
   - Confirm new password

2. **Admin Tab Management**:
   - Settings → Admin Tabs
   - Check/uncheck tabs to require admin access
   - Changes apply immediately

3. **Advanced Configuration**:
   - Project naming patterns
   - Folder template editing
   - Plugin management

## Settings and Configuration

### Directory Settings

**Configure working directories**:
- Use absolute paths for reliability
- Directories are created if they don't exist
- Year folders are added automatically (e.g., /2024/)

### Tab Settings

**Manage tab visibility**:
- Check to enable, uncheck to hide
- Changes apply immediately
- Admin tabs only visible in admin mode
- Reorder tabs by adjusting order values

### Blockchain Settings

**Configure available blockchains**:
- Enable/disable specific chains
- Add custom blockchain codes
- Set display colors for UI
- Modify blockchain names

### Performance Settings

**CPU Allocation Strategies**:
- **Conservative (25%)**: For running alongside other apps
- **Balanced (50%)**: Default, good for most uses
- **Aggressive (75%)**: When performance is priority
- **Maximum (100%)**: Dedicated processing
- **Single Core**: For compatibility
- **Custom**: Set specific core count

### Notification Settings

**Configure alerts via**:
- **Zapier**: Webhook URL for integrations
- **Slack**: Direct Slack notifications
- **SMS**: Text message alerts

**Test notifications before relying on them!**

## Notifications

### Setting Up Notifications

1. **Zapier Integration**:
   - Create Zapier webhook
   - Enter webhook URL in settings
   - Test with "Test Notification" button

2. **Slack Notifications**:
   - Generate Slack webhook URL
   - Configure in Settings → Notifications
   - Choose channels for different alert types

3. **SMS Alerts**:
   - Requires SMS service webhook
   - Configure phone number in service
   - Limited to critical alerts

### Notification Types

- **Success**: Operation completed successfully
- **Warning**: Operation completed with issues
- **Error**: Operation failed
- **Progress**: Long-running operation updates

## Keyboard Shortcuts

### Global Shortcuts
- `Ctrl+O`: Open directory selector
- `Ctrl+S`: Open settings
- `Ctrl+L`: View logs
- `Ctrl+Tab`: Next tab
- `Ctrl+Shift+Tab`: Previous tab
- `Esc`: Cancel current operation

### Tab-Specific Shortcuts
- `Enter`: Start/confirm operation
- `Space`: Toggle selections
- `Ctrl+A`: Select all (where applicable)
- `Delete`: Remove selected items

## Troubleshooting

### Common Issues and Solutions

**"No tabs are visible"**
- Go to Settings → Tabs
- Enable desired tabs
- Ensure you're in admin mode for admin tabs

**"Permission denied" errors**
- Run application as administrator
- Check directory permissions
- Ensure antivirus isn't blocking

**"Operation failed" messages**
1. Check the logs (View Logs button)
2. Verify master directory is set
3. Ensure sufficient disk space
4. Check file permissions

**Slow performance**
- Adjust CPU allocation in Settings → Performance
- Close other applications
- Process smaller batches
- Check available RAM

**Missing images or files**
- Verify correct directory selected
- Check file extensions match filters
- Ensure files aren't locked by other apps

### Getting Help

1. **Application Logs**:
   - Click "View Logs" button
   - Filter by error level
   - Search for specific operations
   - Export logs for support

2. **Error Messages**:
   - Note exact error text
   - Check when error occurs
   - Try operation with different settings

3. **Support Resources**:
   - GitHub Issues page
   - Documentation wiki
   - Community Discord

## Best Practices

### File Organization

1. **Consistent Naming**:
   - Use standard date format: MM.DD.YYYY
   - Uppercase book names
   - Include blockchain codes

2. **Directory Structure**:
   - Keep approval and render separate
   - Organize by blockchain then type
   - Archive completed projects

### Performance Optimization

1. **Batch Processing**:
   - Process similar items together
   - Use off-peak hours for large jobs
   - Monitor system resources

2. **Resource Management**:
   - Close unused tabs
   - Clear old logs periodically
   - Archive completed projects

### Data Safety

1. **Backups**:
   - Regular backup of master directory
   - Export configurations periodically
   - Keep project archives

2. **Validation**:
   - Preview changes before applying
   - Use dry-run modes when available
   - Verify outputs match expectations

### Workflow Efficiency

1. **Template Usage**:
   - Create reusable project templates
   - Standardize naming conventions
   - Document custom workflows

2. **Automation**:
   - Set up notification webhooks
   - Use batch operations
   - Create plugin tabs for repeated tasks

## Advanced Tips

### Custom Workflows

1. **Plugin Development**:
   - Use Plugin Manager to add custom tabs
   - Start with provided template
   - Test thoroughly before deployment

2. **Integration Options**:
   - Webhook notifications for automation
   - Command-line arguments for scripting
   - Configuration file for defaults

### Performance Tuning

1. **Large Projects**:
   - Split into smaller batches
   - Use incremental processing
   - Monitor memory usage

2. **Network Operations**:
   - Configure appropriate timeouts
   - Use local caches when possible
   - Handle connection failures gracefully

Remember: The application is designed to be intuitive. When in doubt, hover over buttons for tooltips, check the tab description, or consult the logs for detailed information about what's happening.