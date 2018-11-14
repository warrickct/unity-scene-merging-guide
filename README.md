# unity-scene-merging-guide
Just a quick guide on how to set up scene merging for unity.

## Setting up merging tool



## Setting up git

1. Should be located in C:\Program Files\Unity2018.2.6f1\Editor\Data\Tools\UnityYamlMerge.exe (or something similar).

2. Go to your global git config file. Should be located in C:\Users\<your user>\.gitconfig and open this file in a text editor.

3. Append the following to the end of the .gitconfig file: 
```
[merge]
    tool = unityyamlmerge

[mergetool "unityyamlmerge"]
trustExitCode = false
cmd = '<path to UnityYAMLMerge>' merge -p "$BASE" "$REMOTE" "$LOCAL" "$MERGED"
```

4. Download a merge tool and set it up, in my case I used diffmerge: [download here](https://sourcegear.com/diffmerge/)

5. Configure the merge tool to work with git. For diffmerge: [instructions here](https://sourcegear.com/diffmerge/webhelp/sec__git__windows__msysgit.html)

6. At this point set up will be complete.

## Using the UnityYamlMerge tool

1. Attempt a merge a with two branches that have conflicting scene changes.

2. Run the command `git mergetool --tool=unityyamlmerge` to specify the scene merging tool.

3. Unityyamlmerge will then resolve most conflicts automatically and open up your merging tool for you to resolve remaining conflicts manually.

4. Save and exit the merge tool, and commit the changes to complete the merge.
