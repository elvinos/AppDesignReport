
# Technical Research

## Content Management System

A content management system (CMS) is defined as a piece of software which provides a level of automation for the tasks required to effectively manage content. It is usually server-based, interacting with content stored in a repository; this may be located on the same server \cite{p1}. In web development, the ultimate purpose of such tools is to allow an administrative user to edit the content on web page without having to append code files directly.

The CMS used for the IXN project was WordPress.  There are other free, open-source CMS options, such as Drupal or Joomla, but WordPress was selected due to a few critical advantages.These can be boiled down to:

1) Better support options and availability
2) Superior access to themes and add-ons
3) Easy website maintenance.

### Support Options and Availability 

WordPress support is available on a plethora of developer channels for web developers and beginners alike on a myriad of platforms. These include docs, handbooks, codex, Slack channels and Stack Exchange to name a few. Being the most popular CMS, there are entire websites dedicated to support in addition to thousands of online tutorials.
Unlike WordPress, finding expert support for Joomla or Drupal is not quite so simple. All of the platforms provide extensive primary source documentation, but because of WordPress’s popularity, it outshines its competitors as far as ease of access to efficient troubleshooting. 

### Access to themes and add-ons 

While Drupal and Joomla also both offer themes and add-ons, the access and variety are not comparable to WordPress, which offers around 40,000 additional plugins.  In Joomla, there is a feature that allows users to add install from web features for extensions. However, in order to access a template, a user would still have to manually search templates and then install them by adding their URL, which is a bit more arduous that the streamlined WordPress process using the dashboard. Worse still, Drupal users have to have to exit their site, search for the module and theme they want, find the zip file URL and submit the URL to the Modules or Themes page to install them. 


Not only does WordPress take minutes to install, but also the dashboard interface after the install is simple and easy to navigate. This is especially useful if you are developing a simple site for a client and they want to be able to manage and modify the site easily. When WordPress undergoes updates, the process is seamless and developers usually won’t have to make any changes. It should also be mentioned that WordPress has an app from which one can manage their site. Joomla’s post-install panel is not as intuitive and has many more features. Seasoned web developers may prefer this, but for simplicity, WordPress wins out. Drupal offers users ‘distributions’, particular to the type of site that they want to develop. This could be a bit confusing for beginners. Finally, Drupal’s updates can require developer knowledge \cite{p2} \cite{p3} \cite{p4} .

### Bedrock and Trellis

Bedrock is a secure way to install and manage WordPress, implementing an alternative to the conventional WordPress structuring.

Traditionally, WordPress can be installed on both a local device and also a production server, having a Git repository for a sites theme. In this case, deployment means a Git pull of the repository from the server or FTP of the theme. In some cases, the whole site, including WordPress files can be kept under Git as well \cite{p6} .

This approach is troublesome because when WordPress/plugin updates occur, the production site can be broken. To illustrate, after writing code in order update some updated WordPress or plugin functionality, it is time to deploy. When a developer does so, they must install or update the correct version of the plugin on the production site, compile assets, update the theme on the remote server, and then ensure the plugin has been activated on the production site.  This manual and laborious approach is quite error prone and can lead to downtime.

Bedrock is a modern WordPress stack that brings more automation to web development and site maintenance and does so using a better folder structure. (fig 1) It uses PHP doting for environment variables, which are part of the twelve-factor app, a methodology created by Heroku for building web apps\cite{p5}. The main goal of this methodology is to improve work on a growing codebase. The details of underlying principles of this methodology are beyond the scope of this work, but can be found in reference 6 \cite{p8} .

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph20.png}
      \caption{Difference between Bedrock and standard Wordpress Structure}
 \end{figure}

 Composer, a tool for dependency management in PHP,  is used to pull in both .dotenv and WordPress, along with WordPress plugins \cite{p7} . Suppose a developer has a project that depends on a number of libraries and some of those libraries depend on other libraries. In essence, Composer allows the developer to declare the libraries they depend on and finds out the correct versions of packages needed and installs them into the project \cite{p8} .

Bedrock also makes use of Capistrano, a remote server automation tool, for automated deployments \cite{p9}. Vagrant is used to implement easy-to-use development environments. It is a virtual environment manager with a focus on automation \cite{p10} .  Vagrant provides work environments that are easy to configure, reproducible, and transportable controlled by a single reliable workflow. To do so, machines are provisioned on top of a virtualiser, such as VMWare or VirtualBox. Then, industry-standard provisioning tools such as shell scripts, Chef, or Puppet, can automatically install and configure software on the virtual machine \cite{p10} .

The combination of Ansible, an IT automation/server configuration tool, and bedrock give us Trellis \cite{p11}. Ansible is used for automation of cloud provisioning, configuration management, application deployment, and many other IT needs \cite{p12}. The combination of the Bedrock structure and Ansible automation means that Trellis allows WordPress developers to create and manage more professional server environments almost automatically.

An alternative to using Trellis would be MAMP, which has distinct disadvantages. With MAMP, a developer is tied to the versions of the software that MAMP precludes. Updates may be made, to PHP 5.6 for example, but the local MAMP install would be different from your shared host, or VPS, or dedicated server. The differences between the environments of your host machine with MAMP and that of a remote server can cause issues during deployment. This can also cause problems when something goes wrong on your production server and you can’t replicate it on your local machine or vice versa \cite{p13} .  Trellis creates staging and production environments, meaning that’s the staging/production server matches your development virtual machine.



## Front-End
As the name would suggest, front-end development encompasses the creation of the parts of a website with which the user interacts, through the use of technologies such as HTML, CSS, and JavaScript.  In other words, this is where the site’s content, styling and dynamic interface is coded.

HyperText Markup Language, or HTML, is the backbone of the IXN website. This is where the site’s content is kept. It is in the HTML documents where a developer uses PHP to connect the site with the content management system.

The site’s styling was done using SCSS, a version of cascading style sheet (CSS) written for SASS, a program written in Ruby that assembles CSS style sheets for a browser. The advantage of using SASS is that is has added functionality, allowing the use of variables, nested rules, mixins and more within CSS-compatible syntax \cite{p14} .  

Because the IXN website will be accessed from many different devices with different screen sizes, responsive design principle were used during front end development. In order to achieve
a consistent, responsive interface, Bootstrap 4, a front-end web framework based on CSS styling, was used. It has set of fixed classes that allow developers to quickly create applications that scale to devices of all sizes. Additionally, Bootstrap aids developers in adding common components such as navigation bars and panels to a site. It has become the industry standard for responsive web development \cite{p15} .  

In order to add dynamic functionality to the IXN website JavaScript (JS) was used.  JS is a front-end development language which many websites employ and it is supported by all modern web browsers. JQuery is a JavaScript library that simplifies animation, event handling and much more. It was also used to add functionality to the IXN website \cite{p16}.

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph18.png}
      \caption{Front-End and Back-End interaction}
 \end{figure}

## Back-End
Back end development refers to the server -side code written to ensure that a site is robust and usable. This is the code that is run on the server and is responsible for things such as database interactions, logic, and calculations. For the IXN website, PHP was used for server-side scripting in order to query the MariaDB database \cite{p17} .  

Since WordPress was used as the content management system, it was also deployed on our server so that content could be updated via the user-friendly dashboard. This would then update the database, and strategically placed PHP embedded in HTML would then be used to display the content on the appropriate part of the site.

Blade, a templating engine was used in conjunction with PHP, which can be detected when the file extension blade.php is used. Blade employs the concepts of template inheritance and sections. The *@section* notation allows for easy organisation of a site and it can be see embedded in the html. The *@extends* notation can be used in order to inherit other layouts. These tools are extremely convenient for effectively organising code \cite{p18} .  

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph17.png}
      \caption{Front-End and Back-End interaction}
 \end{figure}

 \newpage