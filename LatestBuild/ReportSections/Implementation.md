
# Implementation

## Communication

Most group communication was done on Slack, but other social media messaging channels were also used on occasion. Trello was used to organize and track the progress of group tasks. This tool was also used to share ideas during the HCI portion of the project. If a member couldn’t be present, FaceTime meetings were also used.

## Remote Server

Trellis was used to set up a remote server to be used for the IXN website’s development. When Trellis sets up a local development environment, it automatically creates a server, provisions it, and installs WordPress \cite{p21} . This is done by Vagrant in Trellis, by which a Vagrantfile uses the Ansible provisioner to run dev.yml to set up a virtual machine on the WordPress site using VirtualBox \cite{p22} .

This was done through a few simple steps. First, the site was configured based on the WordPress Sites docs. Then, group_vars/development/wordpress_sites.yml and group_vars/development/vault.yml were edited. Finally, vagrant up was run from the command line from the Trellis folder in the site directory.  

To create a remote server from the remote development environment, a couple of extra steps were needed: Provision and Deploy. Provisioning was done in order to ensure MariaDB and Nginx were installed, Nginx was configured, and a database was set up for the IXN site. The server was provisioned using server.yml. Deployment was done using deploy.yml which took the codebase from GitHub, ran Composer, created config files and reloaded Nginx. \cite{p23}.

## Development Tools

After prototyping using Sketch was completed, each team member took responsibility for the development of specific sections of the site. CodePen was used to make each component for the website before all of the sections were integrated into the appropriate page layouts. The benefit of using CodePen is that HTML, CSS and JavaScript code can be written in the browser, and compiled in real time, with the result visible in the same window. \cite{p19}  Ultimately, it allows for faster development and easy troubleshooting.

From CodePen, the front-end code was integrated into the site’s pages using text editors such as Atom and Sublime, each member had their own preferences. This was where PHP was added. In the later stages of development, all of the code was edited and written using text editors.

**GitHub:**
Finally, GitHub was used for collaboration. Git is a version control system, allowing revisions in the code to be stored neatly and chronologically. The changes can then be seen by other developers who can download and modify it. \cite{p20}  GitHub is the community of developers and where they store their work.

For the IXN website, there was a group repository where code was shared and updated. In order to organize to code and ensure the integrity of the site, five branches were made. There was a branch made for each individual member (Alexcode, PhoebeCode and GioCode). This is where code was written the majority of the time. When updates were finalized, code from these branches was then pushed to the Dev branch. After this code was reviewed and if there were no clashes, the code was then pushed to the master branch which housed the cleanest and most current version of the site at any given time. 

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph15.png}
      \caption{Post implementation annotated MoSCoW}
 \end{figure}

## Build Cycle

The build cycle for the implementation of the IXN project was a process strongly based on iteration. Each team member was assigned individual components to design, construct and implement. This decision was made to streamline and facilitate the process making the webpage. 

The process the team has followed for every single component of the site can be summarised in the following steps: 

1.    From the Prototype done by using Sketch extract the final design of the element to be developed, paying careful attention to the exact size in pixels of each one of its parts.
2.    CodePen was used to construct the elements of the website, this tool was chosen because of its ability to display each change made to the HTML and CSS codes in real time.  
3.    The code created on Codepen was then transferred to a text editor and tested in the local environment to create the Front-End of the website. If the code did not perform well the team would fix the bugs starting from step 2 again. 
4.    Once the local environment displayed positive static results, PHP was embedded in the HTML code to enable and simplify the connection to WordPress and the Maria DB database.
5.    Another element was chosen and the iterative process was followed all over again.

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph21.png}
      \caption{Itereation process followed to create the footer of the IXN website}
 \end{figure}
