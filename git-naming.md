### Branch Naming

Branches created should be named using the following format:

```
{story type}-{2-3 word summary}-{azure task id}
```

`story-type` - Indicates the context of the branch and should be one of:

- ft == Feature
- bg == Bug
- ch == Chore
- rf == Refactor

`story-summary` - Short 2-3 words summary about what the branch contains

**Example**

```
ft-resources-rest-endpoints-3456
```

### PR Naming

The PR title should be named using the following format:

```
#[TASK_ID] Story description
```

**Example**

```
#3456 Build out REST Endpoints for Resources (CRUD)
```

### PR Description Template (Markdown)

The description of the PR should contain the following headings and corresponding content in Markdown format.

```md
#### Description of Task?
#### Any background context you want to provide?
#### What are the relevant user stories or tasks links from Azure DevOps?
#### Screenshots (if appropriate)
```

## PR labels
* wip (Work in Progress) – Not ready for review yet
* in review – Awaiting review
* approved – Reviewed and approved
* changes requested – Needs updates
* blocked – Waiting on another PR or task

### Commits

Atomic commits should be made with the format:

```
<type>(<scope>): <subject>``<BLANK LINE> <body> <BLANK LINE> <footer>

```

Any line cannot be longer than 100 characters, meaning be concise.

```<type>``` should be:

 * feature
 * bug
 * chore
 * release
 * refactor
 * documentation
 * style
 * test

```<scope>``` should be something specific to the commit change. For example:

costume
 * flight
 * fighting-style
 * fan-base
 * logo and so on.

```<subject>``` text should:

 * use present tense: "save" not "saved" or "saving"
 * not capitalize first letter i.e no "Carry to safety"
 * not end with a dot (.)

**Message body (optional)** If a body is to be written, it should:

 * written in present tense.
 * include the reason for change and difference in the previous behaviour

**Example**

chore(coveralls): add coveralls yml 