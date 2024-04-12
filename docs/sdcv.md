# sdcv (Stardict Console Version)

Run the following to install sdcv:

```
sudo dnf install sdcv -y
```

Run the following to install a dictionary:

```
cd ~/Downloads/
wget https://web.archive.org/web/20140917131745/http://abloz.com/huzheng/stardict-dic/dict.org/stardict-dictd_www.dict.org_gcide-2.4.2.tar.bz2
sudo tar -xvjf stardict-dictd_www.dict.org_gcide-2.4.2.tar.bz2 -C /usr/share/stardict/dic
```

Use like `sdcv <word>` or use my `define` script in my Bin folder.
