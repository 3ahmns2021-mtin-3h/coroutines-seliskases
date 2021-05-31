# Coroutines

### What are coroutines? 
A coroutine is a function that can suspend its execution until the given YieldInstruction has finished. Thus, coroutines can execute code over a certain number of frames.
Coroutines stop after the GameObject from which it has been called is deactivated or destroyed.

Yield indicates that the method is an iterator and that it’s going to execute over more than one frame, while return, like in a regular function, terminates execution at that point and passes control back to the calling method.

There are different types of yield instructions:
- yield return null: Waits until the next frame before continuing the coroutine
- yield return WaitForSeconds(float seconds): specifies an exact amount of time to wait
- yield return WaitUntil(bool predicate): stops the execution until a delegate evaluates to true
- yield return WaitWhile(bool predicate): waits for a delegate to be false before proceeding
- yield return WaitForEndOfFrame(): Waits until Unity has rendered every Camera and UI element, just before actually displaying the frame

### Advantages of coroutines:
Executing code consecutively using Coroutines is simple and intuitive. Using the yield keyword, Coroutines can be organized as "To-Do Lists" without having to implement countless if-statements. Respectively, implementing design patterns like State Machines only become practical by using coroutines.

### Usecases of coroutines: 
Whenever an action needs to pause, perform a series of consecutive steps or generally takes longer than a single frame, a Coroutine is useful. As stated above, desing patterns like State Machines rely heavily on Coroutines. Also, performance-heavy tasks (not necessarily having to run over multiple frame) like loading a scene can be executed in coroutines, for then they can run in the background using AsyncOperation.

### When not to use coroutines:
Coroutines shouldn't be used for foreground tasks, operations executed in a single frame (if they're not too performance-heavy), or initialization.

### Sources: 
- https://docs.unity3d.com/ScriptReference/Coroutine.html
- https://gamedevbeginner.com/coroutines-in-unity-when-and-how-to-use-them/
- https://stackoverflow.com/questions/65638106/in-which-cases-you-dont-want-or-you-shouldnt-use-coroutines-in-kotlin
- https://www.codinblack.com/how-to-run-a-method-at-certain-time-intervals-in-unity/

Copyright by seliskases
