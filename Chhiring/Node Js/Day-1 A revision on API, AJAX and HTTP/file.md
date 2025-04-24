Revised what is API, AJAX and HTTP in Context to Node.

Ajax:
AJAX is a technique used in web development to update parts of a web page without reloading the whole.
An example would be fetching for a data once the user views a specific contents like on Instagram.
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/data', true);
xhr.onload = function () {
  if (xhr.status === 200) {
    console.log(xhr.responseText);
  }
};
xhr.send();

This thing however has become tideous and now is replaced by Fetch Api which is cleaner, promise-based, and easier to read and write.
