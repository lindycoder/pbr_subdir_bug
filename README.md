# How to reproduce

```
git clone git@github.com:lindycoder/pbr_subdir_bug.git
cd pbr_subdir_bug/subdir
python setup.py sdist
```

This is the actual output
```
running sdist
[pbr] Writing ChangeLog
[pbr] Generating AUTHORS
running egg_info
writing requirements to pbr_subdir_bug.egg-info/requires.txt
writing pbr_subdir_bug.egg-info/PKG-INFO
writing top-level names to pbr_subdir_bug.egg-info/top_level.txt
writing dependency_links to pbr_subdir_bug.egg-info/dependency_links.txt
[pbr] Processing SOURCES.txt
[pbr] In git context, generating filelist from git
warning: no previously-included files found matching '.gitignore'
warning: no previously-included files found matching '.gitreview'
warning: no previously-included files matching '*.pyc' found anywhere in distribution
writing manifest file 'pbr_subdir_bug.egg-info/SOURCES.txt'
warning: sdist: standard file not found: should have one of README, README.rst, README.txt

running check
warning: check: missing required meta-data: url

warning: check: missing meta-data: either (author and author_email) or (maintainer and maintainer_email) must be supplied

creating pbr_subdir_bug-8d104d7
creating pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
making hard links in pbr_subdir_bug-8d104d7...
hard linking AUTHORS -> pbr_subdir_bug-8d104d7
hard linking ChangeLog -> pbr_subdir_bug-8d104d7
hard linking setup.cfg -> pbr_subdir_bug-8d104d7
hard linking setup.py -> pbr_subdir_bug-8d104d7
hard linking pbr_subdir_bug.egg-info/PKG-INFO -> pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
hard linking pbr_subdir_bug.egg-info/SOURCES.txt -> pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
hard linking pbr_subdir_bug.egg-info/dependency_links.txt -> pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
hard linking pbr_subdir_bug.egg-info/not-zip-safe -> pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
hard linking pbr_subdir_bug.egg-info/requires.txt -> pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
hard linking pbr_subdir_bug.egg-info/top_level.txt -> pbr_subdir_bug-8d104d7/pbr_subdir_bug.egg-info
copying setup.cfg -> pbr_subdir_bug-8d104d7
Writing pbr_subdir_bug-8d104d7/setup.cfg
Creating tar archive
removing 'pbr_subdir_bug-8d104d7' (and everything under it)

```

## Expectation :

python setup.py sdist should package requirements.txt test-requirements.txt

so these lines should appear 

```
hard linking requirements.txt -> pbr_subdir_bug-8d104d7
hard linking test-requirements.txt -> pbr_subdir_bug-8d104d7
