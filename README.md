# vasuper-nixos-config
My Nixos Config as it evolves

# Getting started quickly from fresh install of NixOS   

- Install git in a nix shell
```
nix-shell -p git
```

- Clone this Repo
```
git clone https://github.com/Vasu77df/vasuper-nixos-config.git /home/vasuper/.nixos-config/
```

- Remove the existing nix configs
```
# Gotta be sudo perms
rm /etc/nixos/configuration.nix
```

- Symlink configuration.nix to the one in the repo
```
sudo ln -s /home/vasuper/.nixos-config/host/nixos-laptop/configuration.nix /etc/nixos/configuration.nix
```

- Move hardware-configuration.nix to the `.nixos-config` path  and then symlink it from the `.nixos-config` path back to `/etc/nixos/`
```
sudo mv /etc/nixos/hardware-configuration.nix /home/vasuper/.nixos-config/host/nixos-laptop/
sudo ln -s /home/vasuper/.nixos-config/host/nixos-laptop/hardware-configuration.nix /etc/nixos/hardware-configuration.nix
```

- Add root ownership permissions to the
```
sudo chown -R vasuper /home/vasuper/.nixos-config
```

- Now rebuild
```
sudo nixos-rebuild swithch
```

