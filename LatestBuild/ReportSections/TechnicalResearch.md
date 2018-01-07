# Technical Research

## Content Management System

A content management system (CMS) is a piece of software which provides a level of automation for the tasks required to manage content efficiently. It is usually server-based, interacting with content stored in a repository; which can be located on the same server \cite{p1}. In web development, the ultimate purpose of such tools is to allow an administrative user to edit the content on a website without having to append code files directly.

The CMS used for the IXN project was WordPress.  There are other free, open-source CMS options, such as Drupal or Joomla, but WordPress was selected due to a few critical advantages.These can be boiled down to:

1) Better support options and availability
2) Superior access to themes and add-ons
3) Easy website maintenance.

### Support Options and Availability 

WordPress support is available on a plethora of developer channels for web developers and beginners alike on a myriad of platforms. These include docs, handbooks, codex, Slack channels and Stack Exchange to name a few. Being the most popular CMS, there are entire websites dedicated to supporting in addition to thousands of online tutorials.
Unlike WordPress, finding expert support for Joomla or Drupal is more difficult. All of the platforms provide extensive primary source documentation, but because of WordPress’s popularity, it outshines its competitors as far as ease of access to efficient troubleshooting. 

### Access to Themes and Add-ons 

While Drupal and Joomla also both offer themes and add-ons, the access and variety are not comparable to WordPress, which offers around 40,000 additional plugins.  In Joomla, there is a feature that allows users to install extensions. However, to access a template, a user would still have to manually search templates and then install them by adding their URL, more arduous than WordPress streamlined process using the dashboard. Worse still, Drupal users have to exit their site, search for a specific module or theme, find a zip file URL and submit the URL to the Modules or Themes page to install them. 

Not only does WordPress take minutes to install, but also the dashboard interface after the install is simple and easy to navigate \cite{p3}. This is especially useful if you are developing a simple site for a client and they want to be able to manage and modify the site's content easily. Updating Wordpress is a seamless process often requiring no developer interaction. It should also be mentioned that To increase accessibility, WordPress offers a mobile app that users can download to monitor and update their site. Joomla’s post-install panel less intuitive, partly due to offering many more features out of the box \cite{p2}. Seasoned web developers may prefer this, but for simplicity, WordPress wins out. Drupal offers users *‘distributions’*, particular to the type of site that they want to develop. This could be a bit confusing for beginners. Finally, Drupal’s updates can require developer knowledge \cite{p4}.

## Roots Technology Stack: Sage, Bedrock and Trellis

Traditionally, Wordpress app development and deployment involves installing Apache, My SQL and PHP locally, often installed using software such and MAMP or WAMP.
Servers (particularly shared hosting providers) often provide WordPress installs using a one-click install method. This prevents the developer having to configure installation and setup of the production server remotely but limits files to be uploaded via File Transfer Protocol (FTP) only. This method has many limitations and is highly unsuitable for professional website development. Some of the limitations include:

1. No relationship between local and production files creating duplication of work
2. Databases between local and production will be different and hard to sync across
3. If an error occurs when updating production files,  the entire production site can be corrupted suspending the websites service to users
4. FTP sites can be very slow to load and update
5. Plugins and backend changes have to be completed through the control panel and no WP-CLI access is provided \cite{p13}

The Root's open source technologies instead provide a different more and superior approach to Wordpress app development; through creating development and production environments, ensuring that production environments server match the development virtual machine precisely.

To illustrate; after creating a new theme or plugin for a Wordpress site on a local server, it is time to deploy. The Sage starter theme offer out of the box code optimisation technology which requires compiling. Through typing a single line of code a developer can install or update all the correct version of the plugin on the production site, compile assets, update the theme on the remote server, and then ensure the plugin has been activated on the production site while maintaining the database between the local and development sites.  Through using Sage, Bedrock and Trellis in unison, the process of developing, testing and deploying can be reduced to a fraction of the time while the site can be fully optimised and remain online and stable. The following subsections give more detail to the three Roots technologies:

### Bedrock
Bedrock is a modern WordPress stack that brings more automation to web development and site maintenance and does so using a better folder structure, see Figure \ref{bedrockfolder}. It uses PHP *.dotenv* for environment variables, which are part of the twelve-factor app \cite{p6}, a methodology created by Heroku for building web apps\cite{p5}. The main goal of this methodology is to improve work on a growing codebase \footnote{The details of underlying principles of this methodology are beyond the scope of this work but can be found in \cite{p8}.}.

\begin{table}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.85\textwidth]{ph20.png}
      \caption{Difference between Bedrock and standard Wordpress Structure}
\label{bedrockfolder}
 \end{table}

Composer, a tool for dependency management in PHP,  is used to pull in both *.dotenv and WordPress, along with WordPress plugins \cite{p7}. Suppose a developer has a project that depends on some libraries and some of those libraries depend on other libraries. In essence, Composer allows the developer to declare the libraries they depend on and finds out the correct versions of packages needed and installs them into the project \cite{p8}.

### Trellis
Trellis is a Wordpress development and production server tool which creates and manages these machines. Trellis makes use of Ansible, using this software for automation of cloud provisioning, configuration management, application deployment, and many other IT needs \cite{p12}. These are automated across both local and production servers. To create a local environment, a machine must be provisioned on top of a virtualiser, such as VMWare or VirtualBox. Vagrant is then used to implement these development environments. It is a virtual environment manager with a focus on automation \cite{p10}.  Vagrant provides work environments that are easy to configure, reproducible, and transportable controlled by a single reliable workflow. Then, industry-standard provisioning tools such as shell scripts, Chef, or Puppet, can automatically install and configure software on the virtual machine \cite{p10}.

The combination of the Bedrock structure and Ansible automation means that Trellis allows WordPress developers to create and manage more professional server environments almost automatically.

### Sage

Sage (sitting on top of the Trellis, Bedrock stack), provides modern front-end development workflow designed with the idea of creating:

- An advanced workflow
- Minimal HTML5 templates
- Theme wrappers
- Handy tools such as browser sync to automatically compile and check code across a range of device synchronously

## Front-End
As the name would suggest, front-end development encompasses the creation of the parts of a website with which the user interacts, through the use of technologies such as HTML, CSS, and JavaScript.  In other words, this is where the site’s content, styling and dynamic interface is coded.

HyperText Markup Language (HTML), is the backbone of every website. This is where a site’s content is kept. It is in the HTML documents where a developer uses embedded PHP to connect the site to the content management system.

Cascading style sheets (CSS) are where a sites unique style is developed. SCSS is a version of CSS written for SASS, a program written in Ruby that assembles CSS style sheets for a browser. The advantage of using SASS is that is has added functionality, allowing the use of variables, nested rules, mixins and more within CSS-compatible syntax \cite{p14}.  

Resposive design is critical for modern websites since they are accessed from a variety of browsers and screen sizes. To achieve
a consistent, responsive interface, Bootstrap 4, a front-end web framework based on CSS styling, can be used. It has set of fixed classes that allow developers to quickly create applications that scale to a variety of device sizes. Additionally, Bootstrap aids developers in adding conventional components such as navigation bars and panels to a site. It has become the industry standard for responsive web development \cite{p15}.  

To add dynamic functionality to a website JavaScript (JS) is used.  JS is a front-end development language employed by many websites and supported by all modern web browsers. JQuery is a JavaScript library that simplifies animation, event handling and much more. It is also used to add functionality to a website \cite{p16}.

\begin{table}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.8\textwidth]{ph18.png}
      \caption{Front-End and Back-End Interaction}
 \end{table}

## Back-End
Backend development refers to the server-side code written to ensure that a site is robust and usable. This is the code that is run on the server and is responsible for things such as database interactions, logic, and calculations. PHP is a server-side scripting language used to query a database such as MariaDB or MySQL \cite{p17}. MariaDB is a fork of MySQL and as such has the same database structure and indexes. \cite{p24}

If WordPress is used as the content management system, it is also deployed on the server so that content can be updated via the user-friendly dashboard. This then updates the database, and strategically placed PHP embedded in HTML can be used to display the content in the appropriate part of the site.

Blade by Laravel was is a templating engine used in conjunction with PHP, after appending the file extension *blade.php*. Blade employs the concepts of template inheritance and sections. The *@section* notation allows for easy organisation of a site and can be embedded inside HTML code. The *@extends* notation can be used to inherit other layouts. These tools are extremely convenient for effectively organising code \cite{p18} meeting some of the design patterns further discussed in Section \ref{design-patterns}.  

\begin{table}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.98\textwidth]{ph17.png}
      \caption{Front-End and Back-End interaction}
 \end{table}

 \newpage