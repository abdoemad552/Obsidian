There are two types of tags:
1. Light weight tags: 
	* Similar to branch pointer.
	* Doesn't hold any extra information.
2. Annotated tags:
	* Stored as full objects in the Git database.
	* Contain the tagger name, email, and date; have a tagging message;

To create a new annotated tag to the current commit:
```bash
$ git tag -a <tag-name> -m "Tag message"
```

To create new light weight tag to the current commit:
```bash
$ git tag <tag-name>
```

To create a tag on previous commit:
```bash
$ git tag <tag-name> <commit-hash>
```

To show the content of the tag:
```bash
$ git show <tag-name>
```

To show the created tags:
```bash
$ git tag
```

To push a tag to a remote:
```bash
$ git push <remote> <tag-name>
```

To push all tags to the remote:
```bash
$ git push origin --tags
```

If you use git push `<remote> --follow-tags` only annotated tags will be pushed to the remote.

To delete a tag:
```bash
$ git tag -d <tag-name>
```

If you have deleted a tag in your local repo and want to delete it in remote repo:
```bash
$ git push origin :refs/tags/<tag-name>
```

To checkout a tag:
```bash
$ git checkout <tag-name>
```

To create an alias:
```bash
$ git config --global alias.<alias-name> 'Your command'
```