# minecraft-modpack

Fabric **26.3** modpack, managed with [packwiz](https://packwiz.infra.link/). Mods update automatically every time you launch.

## Player setup (one time, Prism Launcher)

1. Install [Prism Launcher](https://prismlauncher.org/) and log in with your Microsoft account.
2. **Add Instance** → Minecraft **26.3** → Mod loader **Fabric** (loader 0.19.5) → OK.
3. Right-click the instance → **Folder**. Open the `minecraft` folder (create it if missing) and put
   [packwiz-installer-bootstrap.jar](https://github.com/packwiz/packwiz-installer-bootstrap/releases/latest/download/packwiz-installer-bootstrap.jar) in it.
4. Right-click the instance → **Edit** → **Settings** → **Custom commands** → tick the box, and set **Pre-launch command** to:
   ```
   "$INST_JAVA" -jar packwiz-installer-bootstrap.jar https://raw.githubusercontent.com/patrickdundas/minecraft-modpack/main/pack.toml
   ```
5. Launch. A small window downloads the mods, then the game starts. Future launches only download changes.

## Admin: updating the pack

From the pack folder with `packwiz` on your PATH:

```
packwiz modrinth add <mod-slug>   # add a mod
packwiz remove <mod>              # remove a mod
packwiz update --all              # update every mod
packwiz refresh
git commit -am "..." && git push
```

Clients and the server pick up the change on their next launch (GitHub's raw CDN can take up to ~5 minutes).
