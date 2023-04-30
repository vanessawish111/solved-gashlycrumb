Download Link: https://assignmentchef.com/product/solved-gashlycrumb
<br>
<a href="https://www.youtube.com/playlist?list=PLhOuww6rJJNMxWy34-9jlD2ulZxaA7mxV" rel="nofollow">https://www.youtube.com/playlist?list=PLhOuww6rJJNMxWy34-9jlD2ulZxaA7mxV</a>

Write a program that prints the line from a file starting with a given letter:

<pre><code>$ ./gashlycrumb.py aA is for Amy who fell down the stairs.</code></pre>

By default, the <code>-f</code> or <code>--file</code> should use the included <code>gashlycrumb.txt</code> file, but can be overridden:

<pre><code>$ ./gashlycrumb.py a -f alternate.txtA is for Alfred, poisoned to death.</code></pre>

The structure of the file is such:

<pre><code>$ head alternate.txtA is for Alfred, poisoned to death.B is for Bertrand, consumed by meth.C is for Cornell, who ate some glass.D is for Donald, who died from gas.E is for Edward, hanged by the neck.F is for Freddy, crushed in a wreck.G is for Geoffrey, who slit his wrist.H is for Henry, who's neck got a twist.I is for Ingrid, who tripped down a stair.J is for Jered, who fell off a chair.</code></pre>

The program should accept one or more letters as positional arguments, printing each line or a message that the given argument is not present in the file:

<pre><code>$ ./gashlycrumb.py x 4 z -f alternate.txtX is for Xavier, stuck through with a prong.I do not know "4".Z is for Zora, smothered by a fleece.</code></pre>

If given no arguments, it should print a brief usage:

<pre><code>$ ./gashlycrumb.pyusage: gashlycrumb.py [-h] [-f FILE] letter [letter ...]gashlycrumb.py: error: the following arguments are required: letter</code></pre>

Or a longer usage for <code>-h</code> or <code>--help</code>:

<pre><code>$ ./gashlycrumb.py -husage: gashlycrumb.py [-h] [-f FILE] letter [letter ...]Gashlycrumbpositional arguments:  letter                Letter(s)optional arguments:  -h, --help            show this help message and exit  -f FILE, --file FILE  Input file (default: gashlycrumb.txt)</code></pre>

The program should reject a bad <code>--file</code> argument:

<pre><code>$ ./gashlycrumb.py -f alskdfusage: gashlycrumb.py [-h] [-f str] str [str ...]gashlycrumb.py: error: argument -f/--file: can't open 'alskdf': [Errno 2] No such file or directory: 'alskdf'</code></pre>

Run the test suite to ensure your program is correct:

<pre><code>$ make testpytest -xv test.py============================= test session starts ==============================...collected 8 itemstest.py::test_exists PASSED                                              [ 12%]test.py::test_usage PASSED                                               [ 25%]test.py::test_bad_file PASSED                                            [ 37%]test.py::test_a PASSED                                                   [ 50%]test.py::test_b_c PASSED                                                 [ 62%]test.py::test_y PASSED                                                   [ 75%]test.py::test_o_alternate PASSED                                         [ 87%]test.py::test_bad_letter PASSED                                          [100%]============================== 8 passed in 0.50s ===============================</code></pre>