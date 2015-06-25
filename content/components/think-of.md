# How can i think of components?

I think the best way to get the components out of the degign is to look for patterns that repeat (with slight variations) across the app. For example, if your app has forms in different pages, it's safe to think that they all will *almost* the same, so having a component `.form` with some classes for its inner components will avoid having to think avoid the implementation of every and each of the forms.

Let's take a look to this twitter screenshot

![Twitter](http://content.screencast.com/users/sainzandres/folders/Jing/media/39f81384-47c3-49b1-b318-3f861d796d31/00000026.png "twitter screenshot")

You see those rounded-corners rectangles? Those are a great candidate for a component. Every section of content there has a common pattern they follow: rounded corners. It would be a good idea to have a `.content-section` that implements that pattern. If later they decide that every section of content has to have squared corners, you just need to change the definition of `.content-section`. Note that the component name doesn't reveal how it will look. Having a component called `.content-section-with-rounded-corners` is not a good idea, because if someone asks for squared corners, the component becomes useless.