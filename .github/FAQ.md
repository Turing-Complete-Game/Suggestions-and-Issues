# FAQ
## Why do I have a circular dependency involving a custom component when the inner circuit would suggest this shouldn't be the case?
For the purpose of circular dependencies, the innards of a custom component are not considered. In an earlier version of the game, they were, but players would run into undebuggable situations where circular dependencies spanned 2 or more custom components. With the addition of nested custom components, this problem is even worse. In programmer parlance you can think of the component boundry as giving a static guarentee, like pure functions.

Another reason for why this guarentee was enforced was that it will be used for important optimizations later.

To fix a circular dependency involving your custom component, you can often either factor things out of the component, split the component or add a register or other memory to buffer the input. Input pins that have an asterisk are often useful for saving values in a custom component. For a pin to get the asterisk, it can not have any path to any output, except through other asterisk pins.


## Why is level scoring locked until the late game?
Scoring used to be available from the beginning, but often players would not progress until they found the best solution. Getting the best score you can find online, with no experience playing the game, is pretty much impossible for most players, leaving them feeling stupid and getting stuck. Additionally, for players that might not have time to both finish the game and optimizing, I prefer they experience the magic of the core part of the game.


## Why are some of my scores are not visible in the online profile?
Because the server validator is temporarily kind of broken. Long story short, circuit simulation used to be much faster, but to fix a bug I had to make it slower. Now a lot of valid solutions hit the validation timeout. Instead of just patching up this issue I will implement something much faster that I have long planned to do anyway.
