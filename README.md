#Create login and signup forms to capture user credentials (email/password).
<!DOCTYPE html>
<html>
<head>
  <title>Login and Signup Forms</title>
  <link rel="stylesheet" type="text/css" href="styles.css">
</head>
<body>
  <div class="container" id="login-form">
    <h2>Login</h2>
    <form>
      <label for="email">Email:</label>
      <input type="email" id="email" required>
      <label for="password">Password:</label>
      <input type="password" id="password" required>
      <button onclick="login()">Login</button>
    </form>
  </div>
  
  <div class="container" id="signup-form">
    <h2>Sign Up</h2>
    <form>
      <label for="email">Email:</label>
      <input type="email" id="signup-email" required>
      <label for="password">Password:</label>
      <input type="password" id="signup-password" required>
      <label for="confirm-password">Confirm Password:</label>
      <input type="password" id="confirm-password" required>
      <button onclick="signup()">Sign Up</button>
    </form>
  </div>

  <script src="script.js"></script>
</body>
</html>
.container {
  width: 300px;
  padding: 20px;
  margin: 20px;
  background-color: #f2f2f2;
}

h2 {
  text-align: center;
}

form {
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 5px;
}

input[type="email"],
input[type="password"] {
  padding: 10px;
  margin-bottom: 10px;
}

button {
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}
.container {
  width: 300px;
  padding: 20px;
  margin: 20px;
  background-color: #f2f2f2;
}

h2 {
  text-align: center;
}

form {
  display: flex;
  flex-direction: column;
}

label {
  margin-bottom: 5px;
}

input[type="email"],
input[type="password"] {
  padding: 10px;
  margin-bottom: 10px;
}

button {
  padding: 10px;
  background-color: #4CAF50;
  color: white;
  border: none;
  cursor: pointer;
}

button:hover {
  background-color: #45a049;
}

#js......
document.getElementById("loginForm").addEventListener("submit", function(event) {
  event.preventDefault(); // Prevent form submission
  var email = document.getElementById("email").value;
  var password = document.getElementById("password").value;
  // Login logic here...
  console.log("Login submitted:", email, password);
});

document.getElementById("signupForm").addEventListener("submit", function(event) {
  event.preventDefault(); // Prevent form submission
  var email = document.getElementById("email").value;
  var password = document.getElementById("password").value;
  // Signup logic here...
  console.log("Signup submitted:", email, password);
});

#Create a form for users to write and submit blog content.
#Implement server-side logic to save blogs in a database, associating them with the logged-in user.
<html>
<head>
    <title>Blog Creation Form</title>
    
</head>
<body>
    <div class="container">
        <h2>Create Blog Content</h2>
        <form id="blogForm" onsubmit="saveBlog(event)">
            <label for="title">Title</label>
            <input type="text" id="title" name="title" required>
            
            <label for="content">Content</label>
            <textarea id="content" name="content" rows="8" required></textarea>
            
            <input type="submit" value="Submit">
        </form>
    </div>
 body {
            font-family: Arial, sans-serif;
        }
        .container {
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #f2f2f2;
        }
        label {
            font-weight: bold;
        }
        input[type="text"],
        textarea {
            width: 100%;
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
        input[type="submit"] {
            background-color: #4caf50;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background-color: #45a049;
        }
    function saveBlog(event) {
            event.preventDefault(); // Prevent form submission

            // Fetch the values from the form
            const title = document.getElementById('title').value;
            const content = document.getElementById('content').value;

            // Simulating server-side logic to save the blog
            // You can use XMLHttpRequest or fetch to make an AJAX request to your server
            // In this example, we'll simply log the blog data to the console
            console.log(`Title: ${title}`);
            console.log(`Content: ${content}`);

            // Reset form fields after submission
            document.getElementById('title').value = '';
            document.getElementById('content').value = '';
        }
#Use a rich text editor to allow users to add text, images, and videos to their blogs.

    <html>
<head>
  <meta charset="UTF-8">
  <title>Rich Text Editor</title>
  
</head>
<body>
  <div class="toolbar">
    <button onclick="formatText('bold')"><b>B</b></button>
    <button onclick="formatText('italic')"><i>I</i></button>
    <button onclick="formatText('underline')"><u>U</u></button>
  </div>

  <div class="editor" contenteditable="true"></div>

  <script>
    function formatText(command, value = null) {
      document.execCommand(command, false, value);
    }
  </script>
</body>
</html>
 .editor {
      border: 1px solid #ccc;
      border-radius: 5px;
      padding: 10px;
      min-height: 300px;
    }

 .toolbar {
      margin-bottom: 10px;
    }
  function insertImage() {
  const imageUrl = prompt('Enter the URL of the image:');
  if (imageUrl) {
    const imgElement = document.createElement('img');
    imgElement.src = imageUrl;
    document.getSelection().getRangeAt(0).insertNode(imgElement);
  }
}

#Implement a comment section for each blog post.
#Allow users to write and submit comments.
#Store comments in the database, linked to the specific blog post.
<div class="blog-post">
  <h2>Blog Post Title</h2>
  <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
</div>


<div class="comment-section">
  <h3>Comments:</h3>
  <div id="comments"></div>
  <form id="comment-form">
    <textarea id="comment-input" placeholder="Write a comment..." rows="4" cols="50"></textarea>
    <button type="submit">Submit</button>
  </form>
</div>
.comment-section {
  margin-top: 20px;
}

.comment-section h3 {
  margin-bottom: 10px;
}

#comments {
  margin-bottom: 10px;
}

textarea {
  width: 100%;
  padding: 5px;
  resize: none;
}

button {
  padding: 5px 10px;
  background-color: #4caf50;
  color: white;
  border: none;
  cursor: pointer;
}
document.addEventListener('DOMContentLoaded', function() {
  // Retrieve existing comments from local storage or initialize an empty array
  let comments = JSON.parse(localStorage.getItem('comments')) || [];

  // Display existing comments
  const commentsDiv = document.getElementById('comments');
  comments.forEach(comment => {
    const commentElement = document.createElement('p');
    commentElement.textContent = comment;
    commentsDiv.appendChild(commentElement);
  });

  // Handle comment submission
  const commentForm = document.getElementById('comment-form');
  const commentInput = document.getElementById('comment-input');

  commentForm.addEventListener('submit', function(e) {
    e.preventDefault();



