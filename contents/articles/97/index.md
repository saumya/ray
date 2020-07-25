---
title: Ansible! The basics.
author: saumya
date: 2020-07-25
template: article.pug
---


Ansible is simpler than it sounds. For a long time I used to avoid it, even to know it. Then the time came to make an automated build for one of my opensource projects. I wrote down the automation and finally the build runs upon each `git push` to the repository. Then I knew that I have written an `Ansible playbook`.

<span class="more"></span>

> Ansible is automation.


Now that does not sound anything to me unless I work in Dev-Ops or operations in an enterprise! 

There are things like 
 - installing a specific server
 - installing specific softwares in that server
 - getting the source-code from somewhere (download from another server)
 - install the code in the server and configure the source and machine to run properly
 - build some software (may be Android App or API service)
 - release these builds (upload the build to some other server)

All these things can be done from a single file. That file is either `.yaml` or `.yml`. Each of this `.yml` file is called an `Ansible Playbook`.

Now a days there are enterprises and companies providing infrastructure at a very low cost or almost free. That makes things very different in terms of building softwares, whether in my own machine or building in these servers. This is just one example of many things which one could do in some other's server(or infrastructure). 

All these are `Ansible` and the way one does it, is with `Ansible Playbook` that means with `.yml` file.

 - Know more about [Ansible][ansible] 
 - Read the [Docs about Ansible][docs]
 - More about [YAML][yaml]

The `.yml` file is more simpler than one thinks. It feels like working with `.xml` or `.json`. It is that simple. So the whole infrastructure and deployment thing is almost came to the developer's side of the  job. We listen a lot of Dev-Ops jobs now a days because of that.

> Ansible automates the development and deployment infrastructure with the ease of a developer.

One can code inside the `.yml` file(the Ansible Playbook) like one does in other programming languages. 





Happy coding.




























[ansible]: https://www.ansible.com
[docs]: https://docs.ansible.com/ansible/latest/index.html
[yaml]: https://yaml.org/







