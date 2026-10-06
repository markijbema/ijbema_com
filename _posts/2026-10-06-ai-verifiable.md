# How to make AI work verifiable

Many engineers complain that instead of coding they are now reviewing all day. With AI we shift the actual work to the
AI but we still need mechanisms to be sure that we trust the output. While parts of it can be automated (tests,
typechecks etc) verifying the intent still falls to a human.

Instead of seeing this as a problem, it is more useful to treat it as an observation:

AI works best if the execution is hard (long, expensive, boring, ...), but the verification is easy.

That way we can learn from solutions we already came up with for faster code reviews, and use that to make code reviews
of AI generated code easier. For example, when we need a big refactor to make a functional change, a common pattern is
to create stacked PRs, where the first PR is a risk-free refactor and the second PR creates the actual change. This is
easier to review for two reasons; first of all, both PRs are smaller. But secondly, and more important, you can review
the PRs in a very different way; in the first PR you only need to verify that the functionality did not change, and in
the second one you can focus on the (probably small) change, without being distracted by large amounts of changed files.

When creating functionality with AI we can think about splitting tasks in the same way. Make sure that the large changes
are easy to review, and make sure that you can easily review the complex changes carefully. You can even choose to do a
big simple change by hand so it is very clear how to review, and then do the more complex change with AI.

For instance, while developing the new Kilo Code VS Code extension we wanted to copy the autocomplete functionality from
the old extension, but wire it up in the new extension. I kept this easy to review for my colleagues by first copying
most of the "library" code (44k lines, which were already reviewed before in the old version) and then let the AI do the
wiring up (based upon how it was done in the old extension) which only added an additional 1k lines.

But this is just an example. Try to think how you and your teammates are able to trust a PR; some other techniques:

- Let the AI write a script to do a large change and review that instead of the change itself.
- Restructure your code in such a way that you know what files require more attention than others.
- Add golden masters for complex code with easily verifiable output; this way the reviewer can ignore the code and only
  look at the output.
- Instead of reviewing the diff manually, review it interactively with an agent, and direct it like you direct it with
  coding, zooming in on issues you as an engineer know are important.
- Leave yakshaves and boy-scout fixes out of your PR; instead spin up an extra parallel agent to fix those, and create a
  PR per fix, as they're typically trivial to review
- Consider coding complex changes by hand, and have the AI review/give feedback instead of creating. This way you make
  sure the engineer writing the code has a deep understanding of the change.

As a team work towards a process so these aren't one offs by one engineer, but policy. A common theme in all these
changes is that they do not change how a review is done, but how an engineer prepares code to be reviewed, so this only
works if the whole team commits to it. A good start would be for each engineer to add to the PR how they think their
colleague can verify the change.

This way engineers can focus on the high-leverage work, and leave the drudgery to AI, while still as a team maintaining
good quality.
