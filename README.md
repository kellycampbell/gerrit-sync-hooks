# gerrit-sync-hooks
Hook scripts for using gerrit with github or gitlab. This lets you use github or another repository for your origin, and use gerrit just for code review.

These scripts are meant to be placed in the gerrit/hooks directory. They run when a patchset is submitted to gerrit for review, and when a change is merged in gerrit.

## ref-update

This script runs when you attempt to push a new patchset into gerrit. It syncs up the gerrit repository with the origin. If it fails, your change won't show up in gerrit until the problem is fixed.

## patchset-created

This runs after a patchset is created in gerrit. This example sends a notification to a slack channel.

## change-merged

This script runs after a change is merged into the master or other branch after code review within gerrit. It pushes the change up to the origin repository.
It can fail due to rebase not working, in which case you might have to manually push to the origin to get things back in sync.
