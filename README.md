# WSL startup scripts

Scripts to get a standard GNU/Linux environment on WSL.


## Usage

- Copy `.wsl_startup` to your home
- Copy `wsl-startup` somewhere in your path
- In `.wsl_startup/enabled`, create symlinks to all scripts you need in `../available`
- Add `source ~/.session_env` to your `~/.bashrc`

Make sure `wsl-startup` is run by the Windows scheduler at every login, so all programs
are started correctly (such as GNOME keyring and its SSH agent).

## License

GNU GPLv3.0

