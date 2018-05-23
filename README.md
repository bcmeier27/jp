# jp
Enhancement of the erstwhile* poofyleek/jp project.

<pre>
Usage: jp.exe [-D] &lt;filename> &lt;operation> ...
        &lt;filename> := &lt;string> | - (standard input)
        &lt;operation> := &lt;leaf-ops> | &lt;func-ops>
        &lt;leaf-ops> := [ len | list | print ] ...
        - len &lt;path> [&lt;path> ...]  (prints the length of &lt;path> element's value as 'len &lt;int>')
        - list &lt;path> [&lt;path> ...]  (prints the value of each &lt;path> listed)
        - print &lt;path> [&lt;path> ...]  (same as list, but with a LF after each value)
        &lt;func-ops> := [ foreach | if ] ...
        - if &lt;path> &lt;logical-op> &lt;value> &lt;operation> ...       ()
        - foreach &lt;arrayPath> &lt;operation> ...
Example:
        $ echo '{"items": [{"title": "tall tales", "author": "tim"},\
                           {"title": "afterwords", "author": "bob"}]}' | \
          jp.exe - foreach items if title ~= "^[aA].*" list author title
Output:
        bob afterwords
</pre>

(*Not sure why or when, but Github user poofyleek has dropped off the face of the earth. All his/her Github content has disappeared.)
