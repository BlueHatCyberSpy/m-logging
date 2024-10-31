# M-Logging "Library"
This is my personal logging and testing "library" for my C projects. Granted,
the functionality is very limited, hence the use of "library" instead of
library. I am not of the belief that entire frameworks are the best option
for debugging and testing code. 

## Usage
The M-Logging "library" comes a few basic functions: `MLOG_log(msg)`, 
`MLOG_error(msg)`, and `MLOG_test(cond, tag)`. This is very important: the 
logging functions will not work unless the macro "MLOG" is defined. There are
more options, such as formatted printing (`MLOG_logf(msg, ...)`, `MLOG_errorf(msg, ...)`,
`MLOG_testf(cond, tag, ...)`). There are also colored options, such as
`MLOG_logc(color, msg)` and `MLOG_testc(cond, color, tag)`. Finally, there are
functions for formatting and color, such as `MLOG_logfc(color, msg, ...)`,
`MLOG_errorfc(color, msg, ...)`, and `MLOG_testfc(color, cond, tag, ...)`.

## Syntax 
```
#include "mlogging.h"

int main(void) {
    /* prints "Hello John Doe" in blue */
    MLOG_logfc(COLOR_BLUE, "Hello %s\n", "John Doe");
    int x = 10;
    /* prints Test "x equals 5": [FAILED] */
    MLOG_test((x == 5), "x equals 5");
}
```
