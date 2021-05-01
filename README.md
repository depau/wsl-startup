# WSL startup scripts

Scripts to get a standard GNU/Linux environment on WSL (WSL1 and WSL2).

Read more on my blog: https://blog.depau.eu/2020/03/05/installing-arch-wsl-manually/

## Usage

- Copy `.wsl_startup` to your home
- Copy `wsl-startup` somewhere in your path
- In `.wsl_startup/enabled`, create symlinks to all scripts you need in `../available`
- Add `source ~/.session_env` to your `~/.bashrc`

Make sure `wsl-startup` is run by at every login, so all programs
are started correctly (such as GNOME keyring and its SSH agent).

To do that you can add a shortcut like so:

1. Copy the `NoConsole.vbs` script to your Windows C: drive.
2. Open Explorer to `%appdata%\Microsoft\Windows\Start Menu\Programs\Startup`.
3. Right-click an empty space, "New" → "Shortcut".
4. Set the location to the `NoConsole.vbs` script you just copied, and set the name
   to whatever you want
5. Right-click the newly created shortcut, open Properties
6. In the "Target" field, at the end add:
   ```
   [SPACE] wsl -- /linux/path/to/wsl-startup
   ```

The `NoConsole.vbs` script will let you run `wsl-startup` without showing a command
prompt window.

## Xorg on WSL2

Vcxsrv needs additional configuration on WSL2, check my blogpost for instructions.

On WSL1 you should enable `40_xorg_setup`, on WSL2 you should use `40_xorg_setup_wsl2`
instead.

## License

GNU GPLv3.0

