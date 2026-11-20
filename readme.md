# Assignment — Student Profile Manager

**Course:** Web Development 1  
**Difficulty:** Medium  
**Estimated completion time:** 60–90 minutes  
**Technologies:** HTML5, CSS, JavaScript, Browser APIs

## 1. Objective

Create an interactive **Student Profile Manager** webpage that allows users to enter their information, save it in the browser, copy and read profile text, and preview a selected profile picture.

Your application must run entirely in the browser without a backend server.

By completing this assignment, you will demonstrate your understanding of:

- Clipboard API: `writeText()` and `readText()`
- Web Storage API: `localStorage`
- HTML file inputs and the JavaScript `File` interface
- DOM manipulation and event handling
- Basic browser security and permissions

## 2. Functional Requirements

### Part A — Student Profile

Create a profile form containing:

- **Full Name** — text input
- **Email Address** — email input
- **Favorite Course** — dropdown with at least three options
- **Profile Summary** — an area that displays the entered information

The profile summary must update when the user changes their information.

### Part B — Clipboard API

Implement two buttons.

**Copy Profile**

- Copy the student's name, email, and favorite course to the system clipboard.
- Use `navigator.clipboard.writeText()`.
- Display a success or failure message.

**Read Clipboard**

- Use `navigator.clipboard.readText()` to read clipboard text.
- Display the retrieved text in a separate area.
- Handle permission denial or unsupported browser behavior gracefully.

Both operations must use `async/await` and appropriate error handling.

### Part C — Local Storage

Implement browser-based data persistence.

**Save Profile**

- Save the name, email, and selected course in Local Storage.
- Use `localStorage.setItem()`.

**Restore Profile**

- Automatically restore saved information when the page loads.
- Use `localStorage.getItem()`.
- Update the displayed profile summary.

**Clear Saved Profile**

- Remove the saved profile information.
- Use `localStorage.removeItem()`.
- Clear the form inputs and refresh the summary.

**Important:** Do not use `localStorage.clear()` to remove all storage for the website.

### Part D — File Input and Image Preview

Allow the user to select a profile picture from their computer.

Requirements:

- Use `<input type="file">`.
- Accept PNG and JPEG images.
- Display the selected file's name, size in bytes, and MIME type.
- Show an image preview after selection.
- Use `URL.createObjectURL()` to generate the preview URL.
- Use `URL.revokeObjectURL()` to release old preview URLs when they are no longer needed.
- Handle the case where no file is selected or the selected file is not a supported image.

**Important:** The image must only be previewed locally. You do not need to upload it to a server.

### Part E — User Experience and Code Quality

Your webpage must:

- Have a clean and organized layout.
- Use appropriate HTML labels and headings.
- Display useful feedback for user actions.
- Handle errors without crashing.
- Use meaningful variable names and readable JavaScript.

You may use regular CSS or Tailwind CSS for styling.

## 3. Expected Page Structure

Your completed page should contain:

**Student Profile Manager**

**Personal Information**

- Full Name
- Email Address
- Favorite Course
- Save Profile button
- Clear Saved Profile button

**Profile Summary**

- Display the user's current information

**Clipboard Tools**

- Copy Profile button
- Read Clipboard button
- Clipboard text display

**Profile Picture**

- Choose Image button
- Filename, size, and type
- Image preview

**Status**

- Messages showing success, errors, or permission restrictions

You may customize the visual design.

## 4. Testing Requirements

Test all the following cases before submission:

| Test                            | Expected Result                                          |
| ------------------------------- | -------------------------------------------------------- |
| Enter student information       | Profile summary updates                                  |
| Click Copy Profile              | Profile information is copied                            |
| Click Read Clipboard            | Clipboard text appears, or an appropriate error is shown |
| Save profile and refresh        | Saved information is restored                            |
| Clear saved profile and refresh | Previously saved information does not return             |
| Select a PNG or JPEG file       | File details and preview are displayed                   |
| Change the selected image       | Preview updates correctly                                |
| Cancel or clear file selection  | No JavaScript error occurs                               |
| Deny clipboard access           | Appropriate error message appears                        |

## 5. Development and Submission

Run your project using a local web server, such as Node.js:

```bash
npx http-server -p 5500 -a 127.0.0.1
```

Open the application using `http://localhost:5500/`.

Submit:

1. `index.html` — your application (JavaScript and CSS may be embedded or separated into their own files).
2. `README.md` — instructions for running the application.
3. A screenshot of the completed webpage.
4. A screenshot showing the profile data restored after refreshing.

Compress the project files into one ZIP if required by your instructor.

## 6. Evaluation Criteria

Your work will be reviewed for:

- Student profile functionality
- Clipboard API implementation
- Local Storage functionality
- File input and image preview
- User experience and code quality

## 7. Important Notes

- Do not store passwords, authentication tokens, or sensitive information in Local Storage.
- Clipboard access may require browser permission and a user interaction.
- The `accept` attribute is a file-picker hint, not a security guarantee.
- A selected file is not automatically uploaded to a server.
- Your application must work without a backend database.
