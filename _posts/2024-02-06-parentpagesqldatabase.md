---
toc: true
comments: true
layout: post
title: SQL Database Parent Page
courses: { compsci: {week: 21} }
type: hacks
---
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cookie Check and Webpage Loader</title>
    <script>
        function checkCookiesEnabled() {
    
            return navigator.cookieEnabled;
        }

        function loadContent() {
            if (checkCookiesEnabled()) {
                // Cookies are enabled, load the iframe
                document.getElementById("main-content").innerHTML = '<iframe src="http://127.0.0.1:4200/csp3-repo//2024/02/06/sqldatabase.html" width="100%" height="600px" style="border:none;"></iframe>';
            } else {
                // Cookies are not enabled, display error message
                document.getElementById("main-content").textContent = "403 Forbidden: Cookies are not enabled in your browser.";
            }
        }
    </script>
</head>
<body onload="loadContent()">
    <div id="main-content">
        <!-- Content will be loaded here based on cookie check -->
    </div>
</body>
</html>