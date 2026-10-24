# Installing MadoNite on a clean Fortnite 16.40 copy

The [v1 release ZIP](https://github.com/EmiiBytee/MadoNite-1640/releases/tag/v1) contains the mod for Mabayu, Homura, Mami, Madoka, Sayaka and Kyoko (the repaired p3 variant plus Mabayu's wrist ribbons as cape-style parts). It includes the modified executable and all 91 package groups: **274 files, 587,047,696 bytes**. It does not include the base game, CarbonLauncher or a backend. See the [README](README.md#current-state-and-credits) for the exact in-game test status.

## Install

1. Use a **Windows Fortnite 16.40-CL-16218553** installation. Close Fortnite and its launcher before copying files. Download and extract **`MadoNite-1640-v1-portable.zip` from the [v1 release](https://github.com/EmiiBytee/MadoNite-1640/releases/tag/v1)**. The repository's **Code → Download ZIP** contains documentation only; the mod files are in the Release ZIP.
2. Back up `FortniteGame\Binaries\Win64\FortniteClient-Win64-Shipping.exe`. If the destination already contains other `pakchunk9xx-WindowsClient_P.*` or `pakchunk1014/1015-WindowsClient_P.*` files, back those up too. A clean installation should not contain this mod's package files.
3. Copy the **contents of the extracted release's `16.40` folder** into the root of your Fortnite `16.40` installation, keeping the `FortniteGame\Binaries\Win64` and `FortniteGame\Content\Paks` subfolders. Allow the executable to be replaced.
4. Verify the copied files in PowerShell, replacing the destination path with your own:

   ```powershell
   powershell -NoProfile -ExecutionPolicy Bypass -File "PATH_TO_KIT\comprobar_mod.ps1" -GameRoot "PATH_TO_FORTNITE\16.40"
   ```

   The checker should report that all 274 files match the manifest. If it reports `FALTA` (missing), `DISTINTO` (different) or `SOBRA` (extra package), fix the copy before launching the game. It compares SHA-256 hashes against `MOD_MANIFEST.json` and does not modify files.

## Locker and backend

For the six outfits to appear in the locker, the account must be granted their CIDs by the backend you use. This kit installs **client files only**; account and server setup is separate.

The current package keeps shared `Pak925` and uses private `Pak915` for Mabayu's physics; her wrist ribbons are `Pak1016`-`Pak1019`. **Do not mix this kit with older test packages**: one earlier variant hid Kyoko's locker card. The hash checker helps catch different or extra files.

## What's in the Release ZIP

- `16.40/`: files to copy over the game.
- `MOD_MANIFEST.json`: relative path, size and SHA-256 for each file.
- `comprobar_mod.ps1`: read-only verifier for any `16.40` destination.
- `README.md`: screenshots, technical approach and current test status.

To undo the installation, restore the original executable and remove only the files added by this kit, using `MOD_MANIFEST.json` as the exact list. Keep any files that were present before installation.
