- [ ] get tmux session
- [ ] bump version in master in VERSION.cmake
- [ ] create tag and stable branch and push everything
```
$ git tag -s v2.5.3-rc1 -m "Minor release with bug fixes and small improvements."
$ git checkout -b stable-2.5.3-rc1
$ git checkout tags/v2.5.3-rc1
$ git push origin --tags
```

- [ ] get changelog
- [ ] create release on github https://github.com/nextcloud/desktop/releases
- [ ] login on the build servers and change the scripts tag and version suffix
- [ ] build it
- [ ] move it to the right place