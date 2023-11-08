# 25340-5

# One For All

Test Details:
1. Create a repo with 3 packages, one with no labels and two with label: ["hii"]
2. Renovate the repo ... with new logic, now we should have 3 update PRs, one with no labels and two with label ["hii"]
3. Update the config with `addLabels: ["hello"]`, this way all packages have labels now.
4. Now modify the labels on the update PR of one of the packages with labels : modification == remove existing label
5. Renovate the repo again
6. Expected:
 - Pakcage with no labels -< gets a new label [has one label ["hello"]]
 - Package with modified labels -< No labels updated, ie. stuck with modified labels [now has no labels]
 - Package with labels which were not modified by user -< Has old labels and new labels both [has two labels ["hii", "hello"]]
