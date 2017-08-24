Multiple SSH Keys settings for different github account
=================================================================


create different public key
---------------------------------

create different ssh key according the article [Mac Set-Up Git](http://help.github.com/mac-set-up-git/)

	$ ssh-keygen -t rsa -C "your_email@youremail.com"

Please refer to [github ssh issues](http://help.github.com/ssh-issues/) for common problems.

for example, 2 keys created at:

	~/.ssh/id_rsa_nrusse02
	~/.ssh/id_rsa_nrussell

then, add these two keys as following

	$ ssh-add ~/.ssh/id_rsa_nrusse02
	$ ssh-add ~/.ssh/id_rsa_nrussell

you can delete all cached keys before

	$ ssh-add -D

finally, you can check your saved keys

	$ ssh-add -l


Modify the ssh config
---------------------------------

	$ cd ~/.ssh/
	$ touch config
	$ subl -a config

Then added

	#activehacker account
	Host github.com-nrusse02
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_nrusse02

	#jexchan account
	Host github.com-nrussell
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_nrussell
