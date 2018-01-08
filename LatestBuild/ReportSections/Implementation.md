
# Implementation

After researching and down-selecting the most appropriate technologies to meet the project requirement goals, a development environment was created and shared amongst all the members of the team. The local development environment was then used to codify the detailed design template (formed at the end of the design phase) into the final product. This section discusses the methodology and workflow of the build cycle and deployment stages within the development phase of the project.

## Local Development

Due to the advantages discussed in Section \ref{roots-technology-stack-sage-bedrock-and-trellis}, Trellis was used to set up a local Ubuntu server on a virtual machine. The virtual machine provided a sandbox to test and develop the IXN website replicating the characteristics of a live production server.  After installing Trellis's dependencies on a developers computer, and configuring specific files; Trellis can be run to create a local development environment automatically; building a local server on a virtual machine, and provisioning a full LEMP stack and Wordpress installation \cite{p21}.

### File Configuration
Configuring of the Trellis requires few simple steps. Within the Trellis file directory a collection of files were edited including:  

- `group_vars/development/wordpress_sites.yml`
- `group_vars/development/vault.yml`

These files configure the server name and allow for multisite installation to be created. Using Ansible's inbuilt encryption software, all `.vault` files were encrypted, preventing any passwords to be read when committing the code to github.com. File setup only required completing once, shared across GitHub to all team members.

### Server Provisioning

Finally, typing `vagrant up` and `vagrant provision` in the command line while in the Trellis directory ran the Trellis software. Vagrant and Ansible did most of the heavy lifting,configuring two Trellis dependency packages, which used a Vagrantfile and a collection of Ansible `*.yml`  files to set up a virtual machine \cite{p22}. By using the Trellis setup, a similar workflow was used to provision and deploy to a production server.

## Development Tools

On completing the design phase discussed in Section \ref{user-interface-design}, the design template was split up into components that were individually codified by each team member, and then brought together into the final Wordpress theme.  Through combining Bedrock with the Sage starter theme with a collection of development tools, an efficient workspace and workflow were used.

### Text Editors / Intergrated Development Environmets (IDEs)

- *CodePen:*  Used to make each component for the website before all of the sections were integrated into the appropriate page layouts. The benefit of using CodePen is that HTML, CSS and JavaScript code can be written in the browser, and compiled in real time, with the result visible in the same window. \cite{p19}  Ultimately, it allowed for faster development and easy troubleshooting, focusing on design problems alone.
- *Atom/ Sublime*: These are lightweight text editors that utilise plugins to give additional functionality. These tools were useful for tweaking the site and writing HTML code
- *PHP Storm:*, An advanced IDE, used predominantly for writing PHP and optimising SCSS code.

### Collaboration
GitHub was used as the version control system for creating the IXN website. Git allows revisions the code to be stored neatly and chronologically. The changes can then be seen by other developers who can download and modify it using tools such as Github Desktop. \cite{p20}  GitHub is the community of developers and where they store their work.
For the IXN website there was a group repository where code was shared and updated. To organise project code and ensure the integrity of the site, five branches were made; two master branches and a branch for each developer (Alexcode, PhoebeCode and GioCode). When updates were finalised, code from the developer branches was merged into the Dev branch.  This code was reviewed, and if there were no clashes, the code could then be pushed to the master branch. The master branch housed the cleanest and most current version of the site at any given time. The master branch was used as the code base for deployment ensuring only stable code would be deployed. Figure \ref{githubcollab} highlights the branch structured used in code collaboration.

\begin{table}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.98\textwidth]{ph15.png}
      \caption{Overview of Github Collaboration Workflow}
\label{githubcollab}
 \end{figure}

### Web Technologies
The following technologies were used to create the front end interface of the IXN website. After using the Trellis development environment, the team could fully focus on creating a Wordpress theme. A theme acts like a skin which sits on top of the Wordpress CMS, providing the interface that users interact with. Using the Sage starter template, the following list of web technologies could be used out of the box.

- *HTML:* used for organising webpage structure
- *Bootstrap 4:* enhancing HTML code through providing easy to use classes making the website responsive. Bootstrap 4 offers many advantages over Bootstrap 3 including an enhanced grid system and SCSS as standard \cite{Differen19:online}
- *SCSS:* a pre-processor styling language providing additional functionality to basic CSS and allowing the styling sheet to be compiled, optimised and minified into a single CSS file named `main.css`. SCSS was organised into three main folders holding the components, layouts and global styles. This framework greatly improved the readability of the code and SCSS *variables*and *mixins* could then be used throughout the files to enable quick revision throughout the entire code base
- *JavaScript + (JQuery):* used to make pages interactive, adding client-side programming functionality to the site. Javascript was used to make the nav-bars interactive, add video and map support among other features
- *PHP 7.1:* used as the server side language to interact with the server pulling out the correct content to display such as news and event post content
- *Larvavel (Blade): * This is the templating engine used to avoid code repetition in keeping with the design patterns discussed in Section \ref{design-patterns}
- *AJAX:* used to allow the website to send and retrieve data from a PHP server asynchronously without refreshing the page. This technology was key to create an effective project post sorter
- *Shell Scripting: * small shell scripts were written to automate database and upload syncing between different server environments

## Build Cycle

To implement the IXN website efficiently, the build cycle highlighted in Figure \ref{designprocess} was followed to allow for an agile development process. Each team member was assigned single components to design, construct and test. This decision was made to streamline and facilitate the process making the webpage testing and tweaking components for different screen sizes and browsers until the element was ready to integrate into the final code base.
The build process can be summarised in the following steps:

1.   Using the Sketch detailed design template, CSS  components could be exported giving the rough parameters for font shape and size
2.    CSS code was placed into CodePen where HTML and JS  were used to construct the component in full-screen size. This tool was chosen due to its' ability to display new changes in the HTML and CSS instantly without the need of any local development setup.
3. Bootstrap 4 code would then be added to, and the code base would be tweaked to make the component fully responsive working in every screen size
4. Code created on Codepen was then transferred to a text editor and integrated into the development site. This was statically tested in the local environment, fixing any integration problems that may have occurred
5. Once the local environment displayed positive static results, PHP was embedded in the HTML code to enable and simplify the connection to WordPress and the Maria DB database.
6. Another element was chosen, and the iterative process was followed all over again.
7. On completion of all components, the integrated site was tested across a range of browsers, and any issues were resolved.

Through following the build cycle, a minimum viable product (MVP) could be quickly created allowing progress to be shown to the client and enhancements to be made with ease.  Figure \ref{buildcycleimg} shows an overview of the different steps of the build cycle.
\begin{table}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.98\textwidth]{ph21.png}
      \caption{An example of the iterative process used to develop all site components, in this case, the footer.}
\label{buildcycleimg}
 \end{table}

## Deployment

On completion of the build cycle, the code base was ready to be deployed to the live production server. Due to the client's relationship with Microsoft, Azure was selected as the production server to use, providing more than enough performance to run the IXN website.

### Azure Setup
Using the Azure dashboard, a new blank Ubuntu 16.0.4 server was deployed on a paid service plan which met the websites performance requirements. The lead developers SSH key added enabling easy access to connect to the remote server. The domain name `ixn.host` was purchased via Namecheap selected due to its low cost. This was directed to the production server using A name records. Finally, to allow inbound connections to the server, port 80 required being changed to open.

### Remote Server Connection
To deploy to the remote server via the local development environment, a couple of extra steps were needed since the production server required Trellis to connect, Provision and Deploy. Provisioning was done to ensure MariaDB, Wordpress and Nginx were installed. Nginx was configured, and a database was set up for the IXN site. The server was provisioned using server.yml. The deployment was done using deploy.yml which compiled the codebase from the master branch on GitHub created config files and reloaded Nginx. \cite{p23}.

Code can be deployed after writing the following lines on the command line in the Trellis directory:

- `ansible-playbook server.yml -e env=production`
- `./bin/deploy.sh production ixn.host`

\newpage