thunderbird-64
---

Are you frustrated that you can't find an updated and trustworthy 64-bit build of Thunderbird? Then this repository is for you. Every time I update the version number in the `release` file, Travis CI will automatically build Thunderbird and post it to the releases page. It's that simple. It would be impossible for me to interfere with it because it would be obvious in `.travis.yml`. You can even compare the checksums shown at the end of each build with the files that you download.

## How it works (detailed)
1. Travis updates its packages and downloads and runs Mozilla's one-step build prerequisite installer.
2. Travis downloads the source. I don't store it in the repo itself (instead of downloading it) because then my computer would have several gigabytes of storage taken up that I don't need. Also, this allows me to put the license on the process that I use for building, and not the code itself being built.
3. Travis installs the dependencies.
4. Travis sets the build options (see the `before_script` section of `.travis.yml` for details).
5. Travis builds Thunderbird.
6. Travis verifies that it has all of the files and calculates their checksums.
7. Travis uploads the release to GitHub.
8. Travis smiles to himself since he just did a lot of work successfully and takes a long nap.

## License
The Apache 2.0 license can be found in the `LICENSE` file at the root of the repository.
