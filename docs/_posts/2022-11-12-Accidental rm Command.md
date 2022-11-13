---
---

It finally happened. After all that time spent laughing at folks suffered from this mistake, I accidentally typed `rm /*` instead of `rm ./*`. 

It happened while I was making this blog site. I had `dev` branch where I was initially experimenting with how some stuff on Jekyll worked and after a little experimenting I felt ready to actually start making this site. So I made a `midnight-theme/dev` branch from `dev` with the intent of eventually merging it back into `dev`. First order of business get rid of everything to I can start fresh from scratch.

```bash
rm /*	# If your new to the terminal, never do this. If not, then feel free to shoot yourself in the foot
```

And that's how I almost deleted everything in my root directory. Thankfully though my root only had directories so nothing happened since I didn't use the `-r` tag.
