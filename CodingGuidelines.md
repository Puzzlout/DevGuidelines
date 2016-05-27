### Important Tips to follow while coding on Puzzlout

1. Querying the database is done once to read data.
2. Please ask before you code when you have a doubt because what you want to do might be achievable using a helper method that exists already.
3. Use existing Helpers and Controllers and avoid duplicating code.
5. Limit comments to clarify new code or add documentation about a class or method. Follow [this example](https://github.com/Puzzlout/FrameworkMvc/blob/master/src/System/Web/HttpRequest/AcceptHttpLanguageParser.php).
6. $_POST, $_GET and other global variables must not be read directly.
7. Place all JavaScript in js files (no embedded js).  
8. If required, create your own css file (no embedded css).
9. Use AJAX request to get data from the PHP server.
10. Follow this rule for CSS: 
  - app-theme.css: colors/fonts/border style
  - app-style.css: position/margins/widths/heights/border size
