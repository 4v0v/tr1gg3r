# timer

## What is it ?
**timer** is a Löve framework library that handle doing action under certain conditions.
I was tired to deal with boolean farms when trying to code complex behaviors for my games.

It's build around [chrono.lua](https://github.com/adnzzzzZ/chrono) and [hump.timer](https://github.com/vrld/hump/blob/master/timer.lua).
Like those two libraries it also handle tweening values.

This library have functions that can be separated in 2 types:
- **Timing functions**: Do an action after/during/every amount of time
- **Update loop functions**: Do an action once, every XX update loop



## API
- **Timer:update(dt)**: Put this in the love.update function.

- **Timer:after(time, action[, after, tag])**:
  - <span style="font-size:smaller;">**time**   = number</span>
  - **action** = function 
  - **after**  = function 
  - **tag**    = string

After an amount of time (in seconds), execute the action function and then the after function.

- **Timer:every(time, action[, count, after, tag])**:
  - **time** = number
  - **action** = function 
  - **count** = number
  - **after** = function 
  - **tag**  = string

Every amount of time, execute the action function.
If there is a count parameter, the every function will execute this number of time then stop then call the after function.
If the action function return false, the every function will stop then call the after function.

- **Timer:during(time, action[,after, tag])**:
  - **time** = number
  - **action** = function 
  - **after**  = function 
  - **tag**    = string

