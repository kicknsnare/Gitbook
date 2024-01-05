# Zeek Package Manager

Zeek Package Manager helps users install third-party scripts and plugins to extend Zeek functionalities with ease. The package manager is installed with Zeek and available with the `zkg` command

Basic usage of zkg;

| Command                    | Description                                                                  |
| -------------------------- | ---------------------------------------------------------------------------- |
| `zkg install package_path` | Install a package. Example (zkg install zeek/j-gras/zeek-af\_packet-plugin). |
| `zkg install git_url`      | Install package. Example (zkg install https://github.com/corelight/ztest).   |
| `zkg list`                 | List installed package.                                                      |
| `zkg remove`               | Remove installed package.                                                    |
| `zkg refresh`              | Check version updates for installed packages.                                |
| `zkg upgrade`              | Update installed packages.                                                   |



## Zeek Packages 1st approach

&#x20;The first approach is using them as frameworks and calling specific package path/directory per usage

## Zeek Packages 2nd approach

The second and most common approach is calling packages from a script with the "@load" method

## Zeek Packages 3er approach

The third and final approach to using packages is calling their package names; note that this method works only for packages installed with the "zkg" install method.





## Execute/Load Package

```bash
#Calling with script
zeek -Cr http.pcap sniff-demo.zeek
#View script contents
cat sniff-demo.zeek @load /opt/zeek/share/zeek/site/zeek-sniffpass
#Calling from path
zeek -Cr http.pcap /opt/zeek/share/zeek/site/zeek-sniffpass
#Calling with package name
zeek -Cr http.pcap zeek-sniffpass

```
