### Labels

This section describes some GitHub labels (markers that can be associated in an issue) to be used on `amlight` and `kytos-ng` organizations, just so it facilitates when it comes to searching, filtering and prioritizing current issues.

#### `priority_[critical|major|medium|low]`

Priority of the issue (or enhancement) in the following order: `priority_critical`, `priority_major`, `priority_medium`, `priority_low`.

#### `<version>`

This label is meant for planning the current issues and enhancements. For example, `2022.1rc1` could be used on any of the repositories, that way, it is expected to be delivered in this version, if the scope changes, then the label version is supposed to be updated accordingly (removed or set a new future version).

Contributors should prioritize picking up issues and enhancements that have a planned version and based on their priority value, if there is no version set yet, then a `next_release` (string) label should be used, and then replaced as soon as the team is done planning the scope of the upcoming version.

Kytos uses this version pattern `yyyy.<number>` (year.number) and NApps use SemVer `[2]`, if both are being released, the NApp issue might have attached both labels on GitHub to facilitate filtering for kytos release scope as well, otherwise, they will only have their specific label if they are being released individually. 

### Examples

This section illustrates some practical queries examples using GitHub API `[1]` that contributors will likely use, these filters can also be used directly on the web page:

- How can you search for all open issues in the `kytos-ng` org with the `2022.1rc1` label?

```
http "https://api.github.com/search/issues?q=org:kytos-ng+label:2022.1rc1+state:open+is:issue&sort=created"

```

- How can you search for all issues closed with the label `2022.1rc1`, issues that were delivered, in the `kytos-ng` org?

```
http "https://api.github.com/search/issues?q=org:kytos-ng+label:2022.1rc1+state:closed+is:issue&sort=created"
```

- How can you search for all open issues in the `amlight` org with the `bug` label?

```
http "https://api.github.com/search/issues?q=org:amlight+label:bug+state:open+is:issue&sort=created"
```

- How can you search for all issues labeled with `priority-critical` and `bug` in the `kytos-ng` org?

```
http "https://api.github.com/search/issues?q=org:kytos-ng+label:priority_critical+label:bug+state:open+is:issue&sort=created"
```



### References

`[1]` GitHub REST API v3 documentation. https://docs.github.com/en/rest/reference/search#search-issues-and-pull-requests

`[2]` SemVer. https://semver.org/
