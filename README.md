# Build-a-Loading-Button-in-JavaScript-

https://www.youtube.com/watch?v=CssyhqEizuI

index.html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Loading Button</title>
        <link rel="stylesheet" href="styles.css">
    </head>
    <body>
        
    <button id="search-button">
        <div>
            <h3>Search</h3>
        </div>
    </button>


        <script src="app.js"></script>    
    </body>
</html>

##

styles.css
#search-button {
    border: none;
    width: 200px;
    height: 50px;
    border-radius: 5px;
    background-color: rgb(219, 18, 58);
    color: rgb(245, 239, 239);
    font-family: "Trebuchet MS", Arial, sans-serif;
    font-weight: 900;
    font-size: 20px;
    transition: all 0.3s;
    display: flex;
    justify-content: center;
    align-items: center;
}

#search-butto:hover {
    background-color: rgb(255, 68, 99);
}

#search-butto:active {
    background-color: rgb(153, 21, 47);
}

#search-button .loading {
    width: 25px;
    height: 25px;
    border-radius: 50%;
    box-sizing: border-box;
    border: 5px solid rgba(0, 0, 0, 0.2);
    border-right-color: rgb(245, 239, 239);
    animation: loading-animation 2s linear infinite;

}

#search-button h3 {
    margin: 0;
    padding: 0;

}

#search-button .loading * {
    display: none;
}

@keyframes loading-animation {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }

}

##

app.js
const searchButton = document.querySelector('#search-button')
const searchButtonContent = document.querySelector('#search-Button div')

searchButton.addEventListener('click', toggleButton)

function toggleButton() {
    searchButtonContent.classList.toggle('loading')
}

