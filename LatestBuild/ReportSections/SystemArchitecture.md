

# System Architecture

In order to be able to create a high performance website, using the latest technologies to optimises run-time and speed up the design process; a stack of Wordpress technologies were used in three-tier system architecture. The stack was run across both local and production servers enabling a testing environment which was fully representative of the production server while all code could be kept offline.

The full open source Roots stack \cite{rootsweb} was selected as it provided all the tools and structure required to develop the project to a professional standard. Figure \ref{systemarchitecture} shows the relationship between the three roots technologies; Sage, Bedrock and Trellis, and their relationship to the system architecture.

\begin{figure}[H]
\centering
\includegraphics[trim = 0 0 0 0, clip, width=0.85\textwidth]{SystemArchitecture.eps}
\caption{Diagram showing the websites systems architecture, highlighting the relationship between different technologies}
\label{systemarchitecture}
\end{figure}

## Design Patterns

Due to the complexity of the IXN website's system architecture, multiple design patterns were used; simplifying development workflow and improving code readability. The Roots Sage starter theme was selected because it offers many design pattern benefits off the shelf. Some of the typical benefits of using design patterns include:

- The ability to reuse large amounts of code \cite{deanDesignPatterns}
- Capture expert knowledge from other developers where design trade-offs have already been evaluated
- Improve communication between the IXN development team

**Strategy:** This is where a family of algorithms are defined and are made interchangeable depending on the client use case \cite{gamma1995design}. This design pattern was used in the handling of JavaScript files, splitting the files into common, main and custom. Different JavaScript files would be loaded dependent on which page was being called.

**Singleton:**  This is where a class is ensured not to have any more than one instance \cite{gamma1995design}. When creating PHP functionality for the website such as Reading Time (*reading_time()*), found on news posts or the string chopper tool (*chop_string()*) these classes where defied once in the *extras.php* file and then called using namespaces. This ensured the classes were only created once and the functionality could be accessed elsewhere in the code (see Figure \ref{ddcode}).

**Template Method:** This is where a skeleton is used to define reusable components for subclasses \cite{gamma1995design}. This means that subclasses can redefine certain steps of the over-arching class without changing the code's structure. Through using the Larval templating engine, a skeleton for each view could be defined in the *app.blade.php*, different templates files could then be selected and swapped out depending on the page selected.

\begin{figure}[H]
\centering
\includegraphics[trim = 0 0 0 0, clip, width=0.75\textwidth]{ddcode.png}
\caption{Overview of project code structure, including singleton design pattern in extras.php}
\label{ddcode}
\end{figure}

\newpage