# What is causing a Yarn Error?

Yarn doesn’t always perform well under heavy loads. Two common solutions are:

Solution 1: **Install Yarn less often**. Put `yarn install` as high up as possible in your Layerfile so that it is cached. When creating complex workflows that contain Yarn, run `yarn install` in the parent Layerfile. 

For example, consider the following graphs:

![Graphic shows the benefit of using inheritance to reduce repetitive use of yarn install](/docs/resources/yarn_install.png)

On the left, `yarn install` runs five times. On the right, `yarn install` only runs once and then is inherited by its children. When appropriate, use the `SPLIT` directive after running `yarn install` to reduce unnecessary repetition.

Solution 2: **Use npm instead**. Yarn and npm have similar speeds when they are cached.
