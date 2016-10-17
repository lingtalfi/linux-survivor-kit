Linux survivor kit
=======================
2016-10-17


minimal alias kit for a linux machine.



When investigating a new machine, if you are not a pro administrator, you will probably
have no shortcuts (assuming pros have better ways to do things).


I figured it took me 10 minutes or more to create basic shortcuts that allow me decent navigation.


So, without further ado, here it is.

Copy paste in your root's .bashrc and continue what you were doing...


```bash
alias aa='vim ~/.bashrc'
alias aas='source ~/.bashrc'
alias aconf='vim /etc/apache2/sites-available/000-default.conf'
alias alogg='tail -f /var/log/apache2/access.log'
alias ar='service apache2 restart'

alias nstart='service nginx start'
alias nstop='service nginx stop'
alias nr='service nginx reload'
alias nconf='vim /etc/nginx/nginx.conf'
alias nsite='cd /etc/nginx/conf.d'
```



