layout should look like this, "Do Not Block:" and "BYPASSES" is only needed if there is actually a value for them.
```
# Screw
# Do Not Block: I really screwed up that presentation, Make sure you screw on the cap tightly.
# BYPASSES: scr3w, 5crew
screw (you|off)
```

"Do Not Block:" should be used to note down commonly used words or phrases that might trigger false positives.<br>
"BYPASSES:" lists variations often used to bypass the filter.

if we have similar badwords like "arse", "arsehat", "arsehead" we try to only block the similar part.
```
# Arse / Arsehat / Arsehead
# BYPASSES: arseh@t, 4rse, ars3head
arse
```

Since we can't block every similar character that might be used interchangeably such as replacing "i" with "l", "!", "|", "İ", "ı", "𝑖", "𝕚", or "ỉ" to bypass filters we will not attempt to block them individually. Instead, you should handle these cases by either normalizing text (replacing such characters yourself) or limiting the number of special characters that can be used.


--------------------- SOON NEW DESCRIPTION<br>
layout should look like this, "Do Not Block:" and "BYPASSES" is only needed if there is actually a value for them.
```
# Screw
# Do Not Block: I really screwed up that presentation, Make sure you screw on the cap tightly.
# BYPASSES: scr3w, 5crew
screw (you|off)
```

"Do Not Block:" should be used to note down commonly used words or phrases that might trigger false positives.<br>
"BYPASSES:" lists variations often used to bypass the filter(so we have quick data to check new regexes against).

if we have similar badwords like "arse", "arsehat", "arsehead" we try to only block the similar part.
```
# Arse / Arsehat / Arsehead
# BYPASSES: arseh@t, 4rse, ars3head
arse
```

Since we can't block every similar character that might be used interchangeably such as replacing "i" with "l", "!", "|", "İ", "ı", "𝑖", "𝕚", or "ỉ" (leetspeak) to bypass filters we will not attempt to block them individually in each regex. Instead, we use a leetMap which we later use to populate regexes.<br>
for example:<br>
we got the regex "sh[i]t" and our leetMap looks like this:<br>
i = 1, !, l, |<br>
h = |-|<br>
now since [i] is in brackets we can tell our program to fill them with the corresponding values of each letter. if a value consists of multiple letters (e.g h = |-|) we have to normalize it manually so |-|ello becomes hello and then gets checked using regex.
