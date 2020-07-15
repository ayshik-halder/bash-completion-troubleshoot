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
<p align="center">
  <i>You can reach me on given below places. Dont forget to star my Repositories and following me on GitHub for more content.</i>

  <p align="center">
    <a href="https://twitter.com/AyshikHalder" target="_blank" alt="Twitter"><img src="https://github.com/ayshik-halder/ayshik-halder/blob/master/readme/twitter-fill.svg" ></a>
    <a href="https://www.linkedin.com/in/ayshik-h-50aba0139/" target="_blank" alt="Linkedin"><img src="https://github.com/ayshik-halder/ayshik-halder/blob/master/readme/linkedin-fill.svg" ></a>
    <a href="mailto:halderayshik@gmail.com" target="_blank" alt="Contact me"><img src="https://github.com/ayshik-halder/ayshik-halder/blob/master/readme/external-link-line.svg"></a>
    <!-- <a href="https://ayshik-halder.github.io" target="_blank" alt="My site"><img src="readme/external-link-line.svg"></a> -->
  </p>
  
</p>
[  
](https://www.designhill.com/email-signature-generator)




