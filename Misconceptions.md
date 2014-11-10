While some other files have a bunch of harassment, I am sure that the staff will be nicer next time we
meet. Meanwhile, I'm here to clear up lots of misconceptions about Sponge. 

Sponge is actually very poorly planned. This is primarily because #nextstep was full of server owners,
and the fact that "faster release times" and "simplified code" is even mentioned or considered
is bullcrap. The feedback was based on what was best for server owners, not software quality.

So let's begin. While this is a work in progress.

Sponge Software Mistakes
----
- Dependency on Forge
  + Reasoning: 
    + Forge is interface level layer. Therefore, Sponge works like this: API -> Implementation -> Forge -> MC Server.
    This will result in decreased performance just by design. Imagine it like this:
    ```java 
    public void executeAPIMethod() {
      implementationInvoke();
    }
    
    public void implementationInvoke() {
      forgeInvoke();
    }
    
    public void forgeInvoke() {
      minecraftServerInvoke();
    }
    
    public void minecraftServerInvoke() {
      // Do stuff
    }
    ```
    So why not just directly implement `minecraftServerInvoke()` instead of bytecode link?
    + Forge developers, or MCP maintainers are allowed to stop at any time. Then, Sponge will be in loads
    of trouble.
- Not reimplemented
  + Reasoning:
    + Multithreading is very limited
    + Fixes to the server code is not possible
    + Usage of delegation to underlying copyrighted code is legally unstable
    + Remapping using ASM is against copyright law. Copyrighted software is designed to be not modifiable
    + Quote from Wikipedia:
    > By withholding source code, the software producer prevents the user from understanding how the software works and from changing how it works
- Porting other implementations to SpongeAPI
  + Reasoning:
    + Will require more effort (which is clearly not shown in any Sponge-releated projects)
    + The reimplemented version will obviously be used more often because performance related fixes
    will be possible

This information may not always be updated as Sponge may choose at their own discretion to modify their
source based on what I have stated. I claim no responsibilty for these changes as I have refused credit
towards helping Sponge after being unfairly treated and harassed by their staff.

FAQ "Just kiddings"
----
