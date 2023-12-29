
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Bookshop</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        header {
            background-color: #333;
            color: #fff;
            padding: 1em;
            text-align: center;
        }

        section {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            padding: 2em;
        }

        .book {
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 8px;
            margin: 1em;
            padding: 1em;
            width: 200px;
            text-align: center;
        }

        button {
            background-color: #4caf50;
            color: #fff;
            padding: 0.5em 1em;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }

        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>Online Bookshop</h1>
    </header>

    <section id="bookList"></section>

    <script>
        // Sample book data
        const books = [
            { id: 1, title: 'Book 1', author: 'Author 1', price: 20.99 },
            { id: 2, title: 'Book 2', author: 'Author 2', price: 15.99 },
            { id: 3, title: 'Book 3', author: 'Author 3', price: 25.99 },
        ];

        // Function to display books
        function displayBooks() {
            const bookList = document.getElementById('bookList');

            books.forEach(book => {
                const bookElement = document.createElement('div');
                bookElement.className = 'book';
                bookElement.innerHTML = `
                    <h3>${book.title}</h3>
                    <p>${book.author}</p>
                    <p>$${book.price.toFixed(2)}</p>
                    <button onclick="addToCart(${book.id})">Add to Cart</button>
                `;
                bookList.appendChild(bookElement);
            });
        }

        // Function to add a book to the cart (dummy implementation)
        function addToCart(bookId) {
            alert(`Book ${bookId} added to cart! (Not implemented in this example)`);
        }

        // Display books when the page loads
        window.onload = displayBooks;
    </script>
</body>
</html>
