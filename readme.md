# Bash-completion troubleshoot @ayshik-halder

> This is a step by step guide to troubleshoot and reconfigure auto tab completion on linux systems.
   >>You can replace the  **/etc/bash.bashrc**  file with the **bash.bashrc** file on my repo. 


First start by checking the basics;

-   Running  **echo $SHELL**  confirmed I was indeed using a bash shell.
 - Running **dpkg -s bash-completion** confirmed bash-completion package was installed.
 - Next I took a look at the **/etc/bash.bashrc** file and I found the section to **“enable bash completion in interactive shells”** had been commented out for some reason. It is not something I would have knowingly done, so the reason why the section was commented out is a bit of a mystery.
 - -   I changed the section from;

	<code>  # enable bash completion in interactive shells
	    # if ! shopt -oq posix; then
	    #  if [ -f /usr/share/bash-completion/bash_completion ]; then
	    #  . /usr/share/bash-completion/bash_completion
	    #  elif [ -f /etc/bash_completion ]; then
	    #    . /etc/bash_completion
	    #  fi
	    #fi
	    
    To

	<code># enable bash completion in interactive shells
if ! shopt -oq posix; then
  if [ -f /usr/share/bash-completion/bash_completion ]; then
    . /usr/share/bash-completion/bash_completion
  elif [ -f /etc/bash_completion ]; then
    . /etc/bash_completion
  fi
fi

-   I saved the /etc/bash.bashrc file
-   Closed my current bash shells
-   Opened a new one and tab completion was working fine again.

> For queries:
Ayshik Halder
[Email:(mailto:halderayshik@gmail.com)
[![facebook](https://cdn1.designhill.com/assets/dh/images/email-signature/social_media/facebook.png)](https://www.facebook.com/ayshik.godshadow)[![instagram](https://cdn1.designhill.com/assets/dh/images/email-signature/social_media/instagram.png)](https://www.instagram.com/ayshik2k)

[  
](https://www.designhill.com/email-signature-generator)




