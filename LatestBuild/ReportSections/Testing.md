
# Testing

## Compatibility & Responsiveness

The team researched which browser simulators to use for testing the compatibility and responsiveness of the IXN website. BrowserStack was an attractive option because of the range of emulators that the tool offers \cite{g6}. BrowserStack offered the possibility of testing the IXN website on a multitude of Operating Systems, Devices and Browsers. The team tested the IXN project on physical devices as well. The results obtained for desktops and laptops are displayed below:

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph7.png}
      \caption{Laptop/Desktop browser testing results}
 \end{figure}

In regards to testing on mobile devices, BrowserStack was the chosen platform. However, physical device testing also played a very important role. The webpage appears fully responsive on the most current browsers, however, as occurred with the desktop devices older versions of software (around 2012/2013) struggle with the design, SCSS and Bootstrap 4. The mobile testing results are displayed below:

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph8.png}
      \caption{Laptop/Desktop browser testing results}
 \end{figure}


## Server Stability Issues

The team has encountered issues in launching the website through Microsoft Azure. The website sporadically shows that the page is not redirecting properly or that the page is in a redirect loop. The problem seems to disappear after the page is reloaded a second time. The team was not able to fix this matter. Future teams working on the IXN project will have to improve configuration between the website and the Azure servers to increase stability and avoid the occasional redirect errors. 


## Acceptance Testing

The IXN User Acceptance Testing (UAT) has been generated around the requirements of the website \cite{g7} . Use Cases have been used to pick and prepare tasks for users to perform during testing. The procedure that the IXN team followed for User Acceptance Testing is the following:
1.    Design tests for users to cover functional scenarios of the website
2.    Select a testing team of individuals from a variety of backgrounds
3.    Perform the tests and record the results
4.    Fix the bugs encountered or improve the inadequate features.

For the IXN website UAT, thirty-five individuals of varied technical backgrounds were asked to complete the tasks given and the time of completion was recorded. The table below summarises the results obtained:

\begin{figure}[H]
      \centering
      \includegraphics[trim = 0 0 0 0, clip, width=0.7\textwidth]{ph4.png}
      \caption{User Acceptance Testing summarized results}
 \end{figure}

## Error Guessing

Error guessing has been put into practice by making the most of the expertise of fellow UCL Computer Science Students. The IXN team asked members of the Department of Computer Science to come up with, consider and assess circumstances in which the software behind the website might have had problems in coping with the requests made. The efficiency of this testing technique depends on the tester’s abilities. In the case of the IXN website, some minor bugs were spotted in the news section. Consequently, the team went on to fixing them.


