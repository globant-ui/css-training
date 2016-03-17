# What do i need to take into account before start changing code?

Facing a major refactor is always complicated, but when it comes to css, the complexity is even bigger. For its own nature, every rule in css it's global unless we do something about it. If we came to a point where we need to refactor, there are probably lots of global styles. For once, we need to figure out a way to cancel those out. Then, we need to figure out a way to add new, modularized, reusable classes without them being override por some legacy global style or`!important`.

Keep in mind that if the codebase is in production, we cannot do this aggressively. We need to come up with a way to make the old css and new css live without interfering with each other, and then, when we're done, we need to be able to remove all the temporary code we added to make both old and new coexist.

Maybe while some of the team is doing the refactor, the rest of the team is implementing new features or fixing bugs. Do they write new css? Do they modified or add to the old codebase? Ideally, they would add to the new, pretty code. But, for that to be possible, an standard have to be defined for all to follow, and you should do that before anyone has the need to write code.

You have to be aware of all this things before you actually change any code. You can skip all this thinking, but you don't want to be forced to consider this things when you already have old and new css and the team doesn't know which direction to go.