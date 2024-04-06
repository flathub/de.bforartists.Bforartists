![Bforartists splash](splash.png)
_Image made by Belzunze, winner of the Bforartists 4.1 Splash Contest, check out his [Artstation](https://www.artstation.com/belzunze)_

This is the repo for the Flatpak version of [Bforartists](https://www.bforartists.de/), based on https://github.com/flathub/org.blender.Blender

The Bforartists Flatpak, while endorsed by upstream, it maintained unofficially. As such, all bug reports related to the Flatpak should be made here to determine if a bug is related to Bforartists or the Flatpak itself.

# Building Instructions
1. Install `flatpak` and `flatpak-builder` from your distro's repo
2. Install the SDK `flatpak install flathub org.freedesktop.Platform//23.08 org.freedesktop.Sdk//23.08`
3. Clone the repo (with `--recurse-submodules` for the shared Flatpak modules)
4. Create a new folder called `build-dir`
5. To build for testing, execute `flatpak-builder --user --install --force-clean build-dir de.bforartists.Bforartists.yaml`. This will build and install Bforartists.

Note that this will compile x264 from source

# Upgrading to the Newest Version
Open `org.bforartists.Bforartists.yaml` and scroll down to this section:
```yaml
sources:
  - type: archive
    url: https://github.com/Bforartists/Bforartists/releases/download/v3.5.1/Bforartists-3-5-1-Linux.tar.xz
    sha256: a179a87cd295c7d1df4aad0aab4c4a2b14665aa21fd2e822b3583bfba6ed5b6a
    strip-components: 0
``` 

Replace the `url` variable with the url of the latest archive (much be from GitHub releases) and `sha256` with the result of `sha256sum <Bforartists tar archive>`. In addition, it's important to check the upstream Blender flatpak repo to see if anything in the manifest has changed.
