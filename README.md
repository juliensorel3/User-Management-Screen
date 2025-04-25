# User-Management-Screen
Overview
This document outlines the specifications for the User Management Screen, which allows administrators to view, filter, and manage user accounts.

Requirements
Display User List: Show a table of users with columns for ID, Username, Email, and Enabled status.

Filter Option: Allow hiding disabled users via a checkbox.

Add New User: Provide functionality to create a new user with required fields and role assignment.

UI Components & Behavior
1. User List Section
Components:

"Hide Disabled User" Checkbox:

Default State: Checked (disabled users are hidden).

Behavior: When unchecked, the table includes disabled users.

Table Columns:

ID (read-only, numeric)

Username (text)

Email (text)

Enabled (boolean, displayed as true/false or icons)

"New User" Button:

Action: Opens a modal/form for adding a new user.

Initial State:

Table loads with enabled users only.

Sample data (for development):

ID	Username	Email	Enabled
1	AdminUser	admin@phworks.net	true
2	Test User	testuser@phworks.net	true
2. New User Modal/Form
Fields:

Username (text input, required)

Display Name (text input, optional)

Phone (text input, optional, with validation for digits)

Email (text input, required, with email validation)

User Roles (dropdown multi-select):

Options: Guest, Admin, SuperAdmin (default: none selected).

Enabled (checkbox, default: unchecked).

Validation:

Highlight missing/invalid fields on submission (e.g., empty username or invalid email).

Behavior:

Closing the modal discards unsaved inputs.

Successful submission refreshes the user list.

Technical Notes
Frontend Framework: [Specify if known, e.g., React/Angular].

API Endpoints:

Fetch users: GET /api/users?hideDisabled={boolean}

Add user: POST /api/users (payload: {username, displayName, phone, email, roles[], enabled}).
