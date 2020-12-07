# miniLogger
## Logging library easy and fast to use with wchar_t support

You can use this like a normal printf()

### example of usage:

```C
#include "logger.h"
int main() {
    //set standard
    setlocale(LC_ALL,"");
    //debug = 1 shows debug output, debug = 0 doesn't show any
    debug = 1;
    // with writeOnText = 1 the library prints on appLog.log file, 
    //with writeOnText = 0 prints on the stdio stream
    writeOnText = 0;
    /*log_normal gives a wprintf that gets automatically redirected to appLog.log file
    if writeOnText == 1*/
    log_normal(L"sample text with some vargs %d\n", 10);
    
    
    log_info(L"sample text with some vargs %c %d", 'b', 10);

    //debug gets printed only if debug == 1
    log_debug(L"sample text");
    log_error(L"sample text");
    
    //log_fatal closes the program with "exit(EXIT_FAILURE);" and gives a fatal error message
    log_fatal(L"sample text");
}
```
![alt text](https://i.imgur.com/pVs2ppd.png)
### WARNING:
#### if you once used, on the stdout, wprintf() or a call to the functions of miniLogger, you should use wprintf() for the whole project or reset the buffer.

### LICENSE
#### The code is distributed under the GNU General Public License V3, for further more information, check the LICENSE file.
