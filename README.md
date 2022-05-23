# unittest_metacorpus

Grouping small corpora as a test case.

## Cloning this repo incl. submodules

    git clone --recurse-submodules -j8 git@github.com:DCMLab/unittest_metacorpus.git
    
`-j8` is available from git >= 2.8 and fetches up to 8 submodules at a time in parallel

## Fetching this repo incl. submodules

To update all submodules to their latest commit on the `main` branch, do

    git submodule update --remote

Then, commit and push.

The following command would leave the current HEADS where they are, no idea what it's useful for. Leaving it for documentation: `git pull --recurse-submodules --jobs=10`


## How to add a new submodule

What we want is to have the gitlinks always point to the current HEAD of `main`, i.e. to track the `main` branch, like this:

    git submodule add -b main git@github.com:DCMLab/frescobaldi_fiori_musicali.git

which will create the submodule `frescobaldi_fiori_musicali` (i.e. with the original repository name) tracking the repo's `main` branch (gitlinks need to be updated on a regular basis, though, see above). The corresponding entry in `.gitmodules` is

    [submodule "frescobaldi_fiori_musicali"]
 	path = frescobaldi_fiori_musicali
  	url = git@github.com:DCMLab/frescobaldi_fiori_musicali.git
  	branch = main

For documentation: The general syntax to add the repository https://github.com/DCMLab/frescobaldi_fiori_musicali as the submodule `ffm` would be `git submodule add git@github.com:DCMLab/frescobaldi_fiori_musicali.git ffm`, which would create a gitlink persistently pointing to the commit of the main branch that is the latest revision at the time being. 
