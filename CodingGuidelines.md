### Important Tips to follow while coding on Puzzlout

1. Querying the database is done once to read data unless:
  a. filters changes
  b. the user session is reset
  c. the application cache is reset
2. Please ask before you code. If not specified, then what you need to do may not be done ***but*** still ask as it might be achievable using a existing code.
3. Classes must follow several principles of [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design). It is better to have the least logic in a class (ideally a class has ***1 responsibility***).
4. Methods must be short. By default, what can be displayed on your screen height is the rule of thumb. But if you have a large screen, 30 lines is the limit to follow.
5. Name variables, methods and classes explicitly. One letter methods or variables for example will be caught by the automatic code analysis and will require a fix.
6. Limit comments to clarify new code or add documentation about a class or method. Follow [this example](https://github.com/Puzzlout/FrameworkMvc/blob/master/src/System/Web/HttpRequest/AcceptHttpLanguageParser.php).
7. $_POST, $_GET and other global variables must not be read directly.
8. Place all JavaScript in js files (no embedded js) unless there is a good reason to do otherwise. In this case, it must be discussed with your manager.  
9. If required, create your own css file (no embedded css).
10. Use AJAX request to get data from the PHP server.
11. Follow this rule for CSS: 
  - app-theme.css: colors/fonts/border style
  - app-style.css: position/margins/widths/heights/border size
