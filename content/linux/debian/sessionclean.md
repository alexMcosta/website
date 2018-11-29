---
title: "Sessionclean"
date: 2018-11-29T08:57:58-08:00
draft: true
---

# `sessionclean`
## Summary
Since Debian has strict permissions over PHP to prevent session hijacking it replaces the wild card garbage collecting of PHP's default garbage collector with a cronjob based error collector.

## What the file looks like
The sessionclean file at the time of this writing is located on my Ubuntu box at `/usr/lib/php/sessionclean` 
```
#!/bin/sh -e
#
# sessionclean - a script to cleanup stale PHP sessions
#
# Copyright 2013-2015 Ondřej Surý <ondrej@sury.org>
#
# Permission is hereby granted, free of charge, to any person obtaining a copy of
# this software and associated documentation files (the "Software"), to deal in
# the Software without restriction, including without limitation the rights to
# use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of
# the Software, and to permit persons to whom the Software is furnished to do so,
# subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
# FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
# COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
"/usr/lib/php/sessionclean" [readonly] 58L, 2922C             6,1           Top
#!/bin/sh -e
#
# sessionclean - a script to cleanup stale PHP sessions
#
# Copyright 2013-2015 Ondřej Surý <ondrej@sury.org>
#
# Permission is hereby granted, free of charge, to any person obtaining a copy oo
f
# this software and associated documentation files (the "Software"), to deal in
# the Software without restriction, including without limitation the rights to
# use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of
# the Software, and to permit persons to whom the Software is furnished to do soo
,
# subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNEE
SS
# FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR
# COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
# IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
                                                              6,1           Top
cat@schrodingersbox:/var/lib/php/modules/7.2/apache2$ cd ../cli/

            if [ "$save_handler" = "files" -a -d "$save_path" ]; then
                proc_names="$proc_names $(echo "$proc_name" | sed -e "s,@VERSION@,$version,")";
                printf "%s:%s\n" "$save_path" "$gc_maxlifetime"
            fi
        fi
    done
done
# first find all open session files and touch them (hope it's not massive amount of files)
for pid in $(pidof $proc_names); do
    find "/proc/$pid/fd" -ignore_readdir_race -lname "$save_path/sess_*" -exec touch -c {} \; 2>/dev/null
done ) | \
    sort -rn -t: -k2,2 | \
    sort -u -t: -k 1,1 | \
    while IFS=: read -r save_path gc_maxlifetime; do
        # find all files older then maxlifetime and delete them
        find -O3 "$save_path/" -ignore_readdir_race -depth -mindepth 1 -name 'sess_*' -type f -cmin "+$gc_maxlifetime" -delete
    done

exit 0
```

