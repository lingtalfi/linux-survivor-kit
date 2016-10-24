Linux survivor kit
=======================
2016-10-17


minimal alias kit for a linux machine.



When investigating a new machine, if you are not a pro administrator, you will probably
have no shortcuts (assuming pros have better ways to do things).


I figured it took me 10 minutes or more to create basic shortcuts that allow me decent navigation.


So, without further ado, here it is.

Copy paste in your root's .bashrc and continue what you were doing...


### Ubuntu14

```bash


alias ll='ls -lArth'

alias aa='vim ~/.bashrc'
alias aas='source ~/.bashrc'
alias aconf='vim /etc/apache2/sites-available/000-default.conf'
alias alog='tail -f /var/log/apache2/error.log'
alias alogg='tail -f /var/log/apache2/access.log'
alias ar='service apache2 restart'


alias nstart='service nginx start'
alias nstop='service nginx stop'
alias nr='service nginx reload'
alias nconf='vim /etc/nginx/nginx.conf'
alias nsite='cd /etc/nginx/conf.d'
alias nlog='tail -f /var/log/nginx/error.log'
alias nlogg='tail -f /var/log/nginx/access.log'


alias pini='vim /etc/php5/fpm/php.ini'
alias pconf='vim /etc/php5/fpm/php-fpm.conf'
alias pconff='vim /etc/php5/fpm/pool.d/www.conf'
alias pstart='service php5-fpm restart'
alias pstop='service php5-fpm stop'
alias psite='cd /etc/php5/fpm/pool.d'
alias plog='tail -f /var/log/php5-fpm.log'


alias vimrc='vim ~/.vimrc'
alias vimt='vim -c "NERDTree" $1'

```



Quick start
------------------

Also to create a nginx php server rapidly on a fresh linux, you can do this:

```bash
apt-get update
apt-get install -y tree
apt-get install -y vim
apt-get install -y nginx
apt-get install -y php5-fpm # on ubuntu16, you can use php7.0-fpm instead
apt-get install -y git
apt-get install -y tmux

# then for security it's recommended that you add this line in your php.ini:  cgi.fix_pathinfo=1 (it will prevent php from
# trying to get a close match to the exact request from the client, which could lead to security issues )

# then, you should configure your vim: https://github.com/lingtalfi/vim-survivor-kit

# add vim syntax highlighting for nginx conf: https://arian.io/vim-syntax-highlighting-for-nginx/
cd
wget -O nginx.vim http://www.vim.org/scripts/download_script.php\?src_id\=19394
mkdir -p ~/.vim/syntax  
mv nginx.vim ~/.vim/syntax/  
vim ~/.vim/filetype.vim  

# (paste the following line in ~/.vim/filetype.vim)
au BufRead,BufNewFile /etc/nginx/*,/usr/local/nginx/conf/* if &ft == '' | setfiletype nginx | endif   
```





