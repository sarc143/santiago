# santiago

a live memory optimizer for 8gb apple silicon macs.

your mac only has 8gb of ram. santiago keeps it from choking. it watches your memory, cpu, and battery, and frees things up before your mac starts swapping to disk and slowing to a crawl.

nothing santiago does is permanent. it never deletes your files. worst case, an app you closed reopens itself.

## install

open terminal (press cmd+space, type "terminal", hit enter) and paste this:

```
curl -sL https://raw.githubusercontent.com/sarc143/santiago/master/santiago -o /usr/local/bin/santiago && chmod +x /usr/local/bin/santiago
```

if that gives a permission error, try:

```
sudo curl -sL https://raw.githubusercontent.com/sarc143/santiago/master/santiago -o /usr/local/bin/santiago && sudo chmod +x /usr/local/bin/santiago
```

it'll ask for your password. that's your mac login password (it won't show as you type, that's normal).

done. type `santiago` to see if it worked.

## what it does

- `santiago status` — check how your mac is doing right now
- `santiago burn` — free up memory without closing anything
- `santiago nuke` — pick which apps to force-quit, one by one
- `santiago start` — run santiago in the background every 15 minutes
- `santiago stop` — turn off the background thing
- `santiago log` — see what santiago has been doing
- `santiago uninstall` — completely remove santiago

## the commands

### status

shows you ram, cpu, gpu, battery, and thermal info at a glance. green means good, yellow means eh, red means bad.

### burn

frees up inactive memory. doesn't close any of your apps. just clears out stuff your mac is holding onto for no reason. run this when things feel sluggish.

### nuke

the big one. shows you every app running on your mac and lets you pick which ones to kill. use arrow keys to move, enter to kill, q to quit. killed apps show (NUKED) so you know what's gone.

### start / stop

`santiago start` makes santiago run `burn` automatically every 15 minutes in the background. you won't notice it's there. `santiago stop` turns it off.

## uninstall

```
santiago uninstall
```

removes everything. the script, the config, the logs, the background task. zero traces.

if the command doesn't work for some reason:

```
rm /usr/local/bin/santiago
rm -rf ~/.santiago
```

same thing.

## config

if you want to tweak thresholds, edit `~/.santiago/config`. but you probably don't need to.

## requirements

- apple silicon mac (m1/m2/m3/m4)
- macos ventura, sonoma, sequoia, or tahoe
- that's it
