# Git post-receive hook for Slack

This is a bash script that posts a message into your slack.com channel
when changes are pushed.

Hook this script into post-receive for your git repositories.

## Configuration

Add an Incoming WebHooks integration in your Slack by going to e.g.
    
    https://yourcompany.slack.com/services/new/incoming-webhook

Make note of the token in the URL.

    git config hooks.slack.token    'D7qgpovcZp3pQ4VmlsYiTIdZ'
    git config hooks.slack.org-name 'yourcompany'
    git config hooks.slack.channel  'general'

## Optional

    git config hooks.slack.username 'git'

Specifies a username to post as. If not specifid, the default name
`incoming-webhook` will be used.

    git config hooks.slack.icon-url 'https://example.com/icon.png'

Specifies an icon to display in Slack instead of the default.

    git config hooks.slack.icon-emoji ':twisted_rightwards_arrows:'

Specifies an emoji icon to display in Slack instead of the default.

    git config hooks.slack.repo-nice-name 'My Awesome Repository'

Specifies a repository nice name that will be shown in messages.

    git config hooks.slack.show-only-last-commit true

Specifies if you want to show only last commits (or all) when pushing
multiple commits



## Linking to Changesets

When the following parameters are set, revision hashes will be
turned into links to a web view of your repository.

    git config hooks.slack.repos-root '/path/to/repos'
    git config hooks.slack.changeset-url-pattern 'http://yourserver/%repo_path%/changeset/%rev_hash%'

For example, if your repository is in /usr/local/repos/myrepo, set repos_root to /usr/local/repos/ and set changeset_url_pattern to http://yourserver/%repo_path%/changeset/%rev_hash% or whatever.
