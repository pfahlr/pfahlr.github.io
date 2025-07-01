<style>
@import url(https://pfahlr.github.io/default.css);
</style>

If you need to work make changes to code under different identities, there are a few different ways you can approach this. The first solution I saw on many webpages was way too clunky for my taste. It involved a modification to your `>

It turns out this is the easiest solution.

If you're not familiar, when first configuring git, you're prompted to configure you name and email. In the `--global` scope like so:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

Well this can also be done without the `--global` option on a per repository basis.

So `cd` into the repository you wish to configure.

You can run the following command to see the current configuration:

```bash
#local 
git config list

#global 
git config list --global
```

now you can set any configuration option you like on a per repository basis. I feel like the best solution to a specific problem is one that, upon learning it, you gain utility beyond the specific thing you were trying to do. This is >

So what settings must be overridden to associate a cloned repository with a specific identity?

In order to do this you'll need to set the `user.name`, `user.email` and to associate with a specific ssh key, you'll use the `core.sshCommand` setting.

So run the following and you'll be good to go:

```bash
git config user.name "Your Name"
git config user.email "<email address>"
git config core.sshCommand "ssh -i ~/.ssh/<your ssh key>"
```

And that's it. Very simple.
