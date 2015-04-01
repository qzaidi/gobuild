How to build
------------

clone or create a symlink to the package to be built inside of src

e.g. 

```
cd src
git clone git@paytm.unfuddle.com:paytm/catalogapp.git paytm.unfuddle.com/catalogapp
```

edit the control file to set package name

create the changelog and update it using dch -v , dch -r when building the package.

run the build command

```
dpkg-buildpackage -us -uc
```

Expectations from package developers
------------------------------------

Create a bin deploy that understands $SRCDIR (git checkout directory) and $PKGDIR - destination where files are to be copied.

Main file should be called app.go and should be inside the parent directory of the package. There should only be one app.go


TODO
----
The editing of control file - if we can avoid this, would be good. Can use the readme.md in package root to automatically figure this out

Credits
-------
This is based on canonicals build system
