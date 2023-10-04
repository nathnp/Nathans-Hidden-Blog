Title: Dirt Simple Site Backups
Date:

# Dirt Simple Site Backups

Both this site, and my [main one](https://nthp.me) are hosted using Blot. Blot has been a fantastic web host, and I love how I do everything locally via git. My sites being synced by git also lets me back them up super easily. 

On one of my Raspberry Pi servers, I have this little script. 

```bash
#!/bin/bash

date

for dir in */; do
  cd "$dir"
  echo "$dir"
  git pull
  cd ..
done

echo""
echo""
```

This script will cd into a folder (in the same directory as the script), run git pull, cd back out, then repeat till it’s gone through all the folders in its directory. Simple. <br>
I have a cronjob set up to run this everyday at 1AM. If I want to add a new site of mine to back up. I just have to clone it into that folder with the script. Easy. 

[Reply to this post via email](mailto:reply.13a8f@nthp.me?subject=Re: Dirt Simple Site Backups)
