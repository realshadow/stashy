# stashy

Python API client for the Atlassian Stash REST API

## Installation

```
pip install stashy
```

## Usage
```python
import stashy
stash = stashy.connect("http://localhost:7990/stash", "admin", "admin")
```

## Examples

* Retrieve all groups

```python
list(stash.admin.groups.all())
```

* Retrieve all users that match a given filter

```python
list(stash.admin.users.all(filter="admin"))
```

* Add a user to a group

```python
stash.admin.groups.add_user('stash-users', 'admin')
```

* Iterate over all projects (that you have access to)

```python
list(stash.projects)
```

* List all the repositories in a given project

```python
list(stash.projects[PROJECT].repos.all())
```

* List all the commits in a pull request

```python
list(stash.projects[PROJECT].repos[REPO].pull_requests.commits())
```

## Status

The following are all the API 1.0 REST endpoints in Stash that have
been implement, with the remainder included using ~~striketrough~~ for
completeness.

* /admin/groups [DELETE, GET, POST]
* /admin/groups/add-user [POST]
* /admin/groups/more-members [GET]
* /admin/groups/more-non-members [GET]
* /admin/groups/remove-user [POST]
* /admin/users [GET, POST, DELETE, PUT]
* /admin/users/add-group [POST]
* /admin/users/credentials [PUT]
* /admin/users/more-members [GET]
* /admin/users/more-non-members [GET]
* /admin/users/remove-group [POST]
* ~~/admin/mail-server [DELETE]~~
* /admin/permissions/groups [GET, PUT, DELETE]
* /admin/permissions/groups/none [GET]
* /admin/permissions/users [GET, PUT, DELETE]
* /admin/permissions/users/none [GET]
* ~~/application-properties [GET]~~
* /groups [GET]
* ~~/hooks/{hookKey}/avatar [GET]~~
* ~~/logs/logger/{loggerName} [GET]~~
* ~~/logs/logger/{loggerName}/{levelName} [PUT]~~
* ~~/logs/rootLogger [GET]~~
* ~~/logs/rootLogger/{levelName} [PUT]~~
* ~~/markup/preview [POST]~~
* ~~/profile/recent/repos [GET]~~
* /projects [POST, GET]
* /projects/{projectKey} [DELETE, PUT, GET]
* ~~/projects/{projectKey}/avatar.png [GET, POST]~~
* /projects/{projectKey}/permissions/groups [GET, PUT, DELETE]
* /projects/{projectKey}/permissions/groups/none [GET]
* /projects/{projectKey}/permissions/users [GET, PUT, DELETE]
* /projects/{projectKey}/permissions/users/none [GET]
* /projects/{projectKey}/permissions/{permission}/all [GET, POST]
* /projects/{projectKey}/repos [POST, GET]
* /projects/{projectKey}/repos/{repositorySlug} [DELETE, POST, PUT, GET]
* ~~/projects/{projectKey}/repos/{repositorySlug}/recreate [POST]~~
* /projects/{projectKey}/repos/{repositorySlug}/branches [GET]
* /projects/{projectKey}/repos/{repositorySlug}/branches/default [GET, PUT]
* ~~/projects/{projectKey}/repos/{repositorySlug}/browse [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/browse/{path:.*} [GET]~~
* /projects/{projectKey}/repos/{repositorySlug}/changes [GET]
* /projects/{projectKey}/repos/{repositorySlug}/commits [GET]
* ~~/projects/{projectKey}/repos/{repositorySlug}/commits/{changesetId:.*} [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/diff/{path:.*} [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/files [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/files/{path:.*} [GET]~~
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests [GET, POST]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId} [GET, PUT]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/activities [GET]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/decline [POST]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/merge [GET, POST]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/reopen [POST]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/approve [POST, DELETE]
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/changes [GET]
* ~~/projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/comments [POST]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/comments/{commentId} [DELETE, PUT, GET]~~
* /projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/commits [GET]
* ~~/projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/diff [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/diff/{path:.*} [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/participants [GET, DELETE, POST]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/pull-requests/{pullRequestId}/watch [POST, DELETE]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/settings/hooks [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/settings/hooks/{hookKey} [GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/settings/hooks/{hookKey}/enabled [PUT, DELETE]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/settings/hooks/{hookKey}/settings [PUT, GET]~~
* ~~/projects/{projectKey}/repos/{repositorySlug}/tags [GET]~~
* ~~/users [GET, PUT]~~
* ~~/users/credentials [PUT]~~
