layout should look like this, "Do Not Block:" and "BYPASSES" is only needed if there is actually a value for them.
```
# Screw
# Do Not Block: should be used to note down commonly used words or phrases that might trigger false positives.
# BYPASSES: scr3w, 5crew
screw
```

"Do Not Block:" is used to note down commonly used words which may trigger false positives.
"BYPASSES:" should list variations or circumventions that users might use to bypass the filter, which we can include for updates or improvements later.

if we have similar badwords like "arse", "arsehat", "arsehead" we try to only block the similar part.
```
# Arse / Arsehat / Arsehead
# BYPASSES: arseh@t, 4rse, ars3head
arse
```
