# VPM Package Template [<img src="https://github.com/JustSleightly/Resources/raw/main/Icons/JSLogo.png" width="30" height="30">](https://vrc.sleightly.dev/ "JustSleightly") [<img src="https://github.com/JustSleightly/Resources/raw/main/Icons/Discord.png" width="30" height="30">](https://discord.sleightly.dev/ "Discord") [<img src="https://github.com/JustSleightly/Resources/raw/main/Icons/GitHub.png" width="30" height="30">](https://github.sleightly.dev/ "Github") [<img src="https://github.com/JustSleightly/Resources/raw/main/Icons/Store.png" width="30" height="30">](https://store.sleightly.dev/ "Store")

[![GitHub stars](https://img.shields.io/github/stars/JustSleightly/VPM-Package-Template)](https://github.com/JustSleightly/VPM-Package-Template/stargazers) [![GitHub Tags](https://img.shields.io/github/tag/JustSleightly/VPM-Package-Template)](https://github.com/JustSleightly/VPM-Package-Template/tags) [![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/JustSleightly/VPM-Package-Template?include_prereleases)](https://github.com/JustSleightly/VPM-Package-Template/releases) [![GitHub issues](https://img.shields.io/github/issues/JustSleightly/VPM-Package-Template)](https://github.com/JustSleightly/VPM-Package-Template/issues) [![GitHub last commit](https://img.shields.io/github/last-commit/JustSleightly/VPM-Package-Template)](https://github.com/JustSleightly/VPM-Package-Template/commits/main) [![Discord](https://img.shields.io/discord/780192344800362506)](https://discord.sleightly.dev/)

A stripped down version of the official VRChat [VPM Package Template](https://github.com/vrchat-community/template-package) that excludes all of the extra website/project bloat.

This is modified from [Dreadrith's template](https://github.com/Dreadrith/Listed-VPM-Template) to support a slightly different workflow.

## Features

- Can clone multiple VPM package templates into one Unity project
- Only auto-builds a GitHub release if there is no existing release tag for the pushed version number when `package.json` is updated
- Automatically builds a GitHub release with a `.unitypackage`, `.zip`, and `package.json` upon pushing a commit change within the package directory
- Automatically adds an icon to the `.unitypackage` that is displays when imported

## Instructions

1. Create a new repository using the green `Use this template` button at the top of this page
2. Clone your new repository onto your PC within an **existing Unity project** in any directory under `Packages/`
    - This will generate a fresh set of GUIDs for each file within this package template and prevent conflicts with other packages
3. Modify the cloned files for your new package
    - Edit `.github/workflows/release.yml`
        - Line 10
        - Line 11
        - Line 12
        - Line 13
    - Rename and Edit `Documentation~/dev.sleightly.template.md` if used
    - Rename and Edit `Editor/dev.sleightly.template.Editor.asmdef` if used
        - "name"
        - "references"
    - Rename and Edit `Runtime/dev.sleightly.template.asmdef` if used
        - "name"
    - Edit `CHANGELOG.md`
    - Edit `LICENSE.md`
    - Edit `package.json`
        - Use [VRChat's](https://vcc.docs.vrchat.com/vpm/packages#vpm-manifest-additions) and [Unity's](https://docs.unity3d.com/2019.4/Documentation/Manual/upm-manifestPkg.html) documentation for reference
    - Replace or remove `thumbnail.png` with your own `.unitypackage` import thumbnail
4. Add any necessary scripts, resources, [samples](https://docs.unity3d.com/2019.4/Documentation/Manual/cus-samples.html), and other files
5. Remove `Documentation~`, `Editor`, `Runtime`, `CHANGELOG.md`, and `LICENSE.md` if unused

## Notes

Folders that end in `~` such as `Documentation~` or `Samples~` are hidden from the Unity Project view within the editor.

Therefore, when the package is exported as a `.unitypackage` whether manually or via automated GitHub workflow, such folders are omitted. The folders are still present in the `.zip` export and when imported through the [VRChat Creator Companion](https://vcc.docs.vrchat.com/vpm/packages/#community-packages)
