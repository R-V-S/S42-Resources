0. Add a console log near the point in your script that you believe isn't working as it should. In this case, you could add one to the very top of your function. You can log anything – just a text string or number would be fine.

0. Does it log to the console? If so, then the problem is deeper inside the function. If not, then the function isn't executing and the problem is outside of the function. Put a console log before the function call.

0. Does that console log work? If so, then maybe there's something wrong with your function call. If not, then the problem is earlier in script execution.

Keep on climbing earlier in script execution and closer to global scope. This is a very simple method of "tracing" your bug by stepping back through execution.

You might very quickly find yourself at the very top of the document and still nothing logging to the console. If this happens, then you should switch to [using the network panel](https://developers.google.com/web/tools/chrome-devtools/network-performance/resource-loading) in your browser's developer tools to determine if the JS file has even loaded. How to use the network panel to check for a file, in a nutshell:

0. Open dev tools (Cmd + option + I on Mac)

0. Choose the network tab

0. Select the "JS" filter

0. Reload the page – does your file appear and have a status of 200? If not, then you'll want to look at your script tag.