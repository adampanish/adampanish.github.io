---
layout: archive
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.10.2/dist/katex.min.css" integrity="sha384-yFRtMMDnQtDRO8rLpMIKrtPCD5jdktao2TV19YiZYWMDkUR5GQZR/NOVTdquEx1j" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.10.2/dist/katex.min.js" integrity="sha384-9Nhn55MVVN0/4OFx7EE5kpFBPsEMZxKTCnA+4fqDmg12eCTqGi6+BB2LjY8brQxJ" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.10.2/dist/contrib/auto-render.min.js" integrity="sha384-kWPLUVMOks5AQFrykwIup5lo0m3iMkkHrD0uJ4H5cjeGihAutqP0yW0J6dpFiVkI" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>
---


<math>
% Don't like 10pt? Try 11pt or 12pt
\documentclass[10pt]{article}
\RequirePackage[T1]{fontenc}

% This is a helpful package that puts math inside length specifications
\usepackage{calc}

% This package helps LaTeX auto-hyphenate hyphenated words if you use
% special hyphens. For example, bio\-/mimicry will properly hyphenate
% ``mimicry'' if necessary.
\usepackage[shortcuts]{extdash}

% Layout: Puts the section titles on left side of page
\reversemarginpar

%
%         PAPER SIZE, PAGE NUMBER, AND DOCUMENT LAYOUT NOTES:
%
% The next \usepackage line changes the layout for CV style section
% headings as marginal notes. It also sets up the paper size as either
% letter or A4. By default, letter was used. If A4 paper is desired,
% comment out the letterpaper lines and uncomment the a4paper lines.
%
% As you can see, the margin widths and section title widths can be
% easily adjusted.
%
% ALSO: Notice that the includefoot option can be commented OUT in order
% to put the PAGE NUMBER *IN* the bottom margin. This will make the
% effective text area larger.
%
% IF YOU WISH TO REMOVE THE ``of LASTPAGE'' next to each page number,
% see the note about the +LP and -LP lines below. Comment out the +LP
% and uncomment the -LP.
%
% IF YOU WISH TO REMOVE PAGE NUMBERS, be sure that the includefoot line
% is uncommented and ALSO uncomment the \pagestyle{empty} a few lines
% below.
%

%% Use these lines for letter-sized paper
\usepackage[paper=letterpaper,
            %includefoot, % Uncomment to put page number above margin
            marginparwidth=1.2in,     % Length of section titles
            marginparsep=.05in,       % Space between titles and text
            margin=1in,               % 1 inch margins
            includemp]{geometry}

%% Use these lines for A4-sized paper
%\usepackage[paper=a4paper,
%            %includefoot, % Uncomment to put page number above margin
%            marginparwidth=30.5mm,    % Length of section titles
%            marginparsep=1.5mm,       % Space between titles and text
%            margin=25mm,              % 25mm margins
%            includemp]{geometry}

%% More layout: Get rid of indenting throughout entire document
\setlength{\parindent}{0in}

% Provides special list environments and macros to create new ones
\usepackage[shortlabels]{enumitem}

% Simpler bibsections for CV sections
% (thanks to natbib for inspiration)
%
% * For lists of references with hanging indents and no numbers:
%
%   \begin{bibsection}
%       \item ...
%   \end{bibsection}
%
% * For numbered lists of references (with hanging indents):
%
%   \begin{bibenum}
%       \item ...
%   \end{bibenum}
%
%   Note that bibenum numbers continuously throughout. To reset the
%   counter, use
%
%   \restartlist{bibenum}
%
%   at the place where you want the numbering to reset.

\makeatletter
\newlength{\bibhang}
\setlength{\bibhang}{0em}
\newlength{\bibsep}
 {\@listi \global\bibsep\itemsep \global\advance\bibsep by\parsep}
\newlist{bibsection}{itemize}{3}
\setlist[bibsection]{label=,leftmargin=\bibhang,%
        itemindent=-\bibhang,
        itemsep=\bibsep,parsep=\z@,partopsep=0pt,
        topsep=0pt}
\newlist{bibenum}{enumerate}{3}
\setlist[bibenum]{label=\arabic*.,resume,leftmargin={\bibhang+\widthof{[999]}},%
        itemindent=-\bibhang,
        itemsep=\bibsep,parsep=\z@,partopsep=0pt,
        topsep=0pt}
\let\oldendbibenum\endbibenum
\def\endbibenum{\oldendbibenum\vspace{-.6\baselineskip}}
\let\oldendbibsection\endbibsection
\def\endbibsection{\oldendbibsection\vspace{-.6\baselineskip}}
\makeatother

%% Reference the last page in the page number
%
% NOTE: comment the +LP line and uncomment the -LP line to have page
%       numbers without the ``of ##'' last page reference)
%
% NOTE: uncomment the \pagestyle{empty} line to get rid of all page
%       numbers (make sure includefoot is commented out above)
%
\usepackage{fancyhdr,lastpage}
\pagestyle{fancy}
%\pagestyle{empty}      % Uncomment this to get rid of page numbers
\fancyhf{}\renewcommand{\headrulewidth}{0pt}
\fancyfootoffset{\marginparsep+\marginparwidth}
\newlength{\footpageshift}
\setlength{\footpageshift}
          {0.5\textwidth+0.5\marginparsep+0.5\marginparwidth-2in}
\lfoot{\hspace{\footpageshift}%
       \parbox{4in}{\, \hfill %
                    \arabic{page} of \protect\pageref*{LastPage} % +LP
%                    \arabic{page}                               % -LP
                    \hfill \,}}

% Finally, give us PDF bookmarks
\usepackage{color,hyperref}
\definecolor{darkblue}{rgb}{0.0,0.0,0.3}
\hypersetup{colorlinks,breaklinks,
            linkcolor=darkblue,urlcolor=darkblue,
            anchorcolor=darkblue,citecolor=darkblue}

%%%%%%%%%%%%%%%%%%%%%%%% End Document Setup %%%%%%%%%%%%%%%%%%%%%%%%%%%%


%%%%%%%%%%%%%%%%%%%%%%%%%%% Helper Commands %%%%%%%%%%%%%%%%%%%%%%%%%%%%

% HEADING
\newcommand{\makeheading}[2][]%
        {\hspace*{-\marginparsep minus \marginparwidth}%
         \begin{minipage}[t]{\textwidth+\marginparwidth+\marginparsep}%
             \centering
             {\LARGE \bfseries #2}\\[0.5em]
             {\large \normalfont Curriculum Vitae}\\[0.15\baselineskip]%
                 \rule{\columnwidth}{0.5pt}%
         \end{minipage}}


% The section headings. Flush left in small caps down pseudo-margin.
%
% Usage: \section{section name}
\renewcommand{\section}[1]{\pagebreak[3]%
    \vspace{1.3\baselineskip}%
    \phantomsection\addcontentsline{toc}{section}{#1}%
    \noindent\llap{\scshape\smash{\parbox[t]{\marginparwidth}{\hyphenpenalty=10000\raggedright #1}}}%
    \vspace{-\baselineskip}\par}

%%% LISTS

% This macro alters a list by removing some of the space that follows the list
% (is used by lists below)
\newcommand*\fixendlist[1]{%
    \expandafter\let\csname preFixEndListend#1\expandafter\endcsname\csname end#1\endcsname
    \expandafter\def\csname end#1\endcsname{\csname preFixEndListend#1\endcsname\vspace{-0.6\baselineskip}}}

% These macros help ensure that items in outer-type lists do not get
% separated from the next line by a page break
% (they are used by lists below)
\let\originalItem\item
\newcommand*\fixouterlist[1]{%
    \expandafter\let\csname preFixOuterList#1\expandafter\endcsname\csname #1\endcsname
    \expandafter\def\csname #1\endcsname{\let\oldItem\item\def\item{\pagebreak[2]\oldItem}\csname preFixOuterList#1\endcsname}
    \expandafter\let\csname preFixOuterListend#1\expandafter\endcsname\csname end#1\endcsname
    \expandafter\def\csname end#1\endcsname{\let\item\oldItem\csname preFixOuterListend#1\endcsname}}
\newcommand*\fixinnerlist[1]{%
    \expandafter\let\csname preFixInnerList#1\expandafter\endcsname\csname #1\endcsname
    \expandafter\def\csname #1\endcsname{\let\oldItem\item\let\item\originalItem\csname preFixInnerList#1\endcsname}
    \expandafter\let\csname preFixInnerListend#1\expandafter\endcsname\csname end#1\endcsname
    \expandafter\def\csname end#1\endcsname{\csname preFixInnerListend#1\endcsname\let\item\oldItem}}

% An itemize-style list with lots of space between items
%
% Usage:
%   \begin{outerlist}
%       \item ...    % (or \item[] for no bullet)
%   \end{outerlist}
\newlist{outerlist}{itemize}{3}
    \setlist[outerlist]{label=\enskip\textbullet,leftmargin=*}
    \fixendlist{outerlist}
    \fixouterlist{outerlist}

% An environment IDENTICAL to outerlist that has better pre-list spacing
% when used as the first thing in a \section
%
% Usage:
%   \begin{lonelist}
%       \item ...    % (or \item[] for no bullet)
%   \end{lonelist}
\newlist{lonelist}{itemize}{3}
    \setlist[lonelist]{label=\enskip\textbullet,leftmargin=*,partopsep=0pt,topsep=0pt}
    \fixendlist{lonelist}
    \fixouterlist{lonelist}

% An itemize-style list with little space between items
%
% Usage:
%   \begin{innerlist}
%       \item ...    % (or \item[] for no bullet)
%   \end{innerlist}
\newlist{innerlist}{itemize}{3}
    \setlist[innerlist]{label=\enskip\textbullet,leftmargin=*,parsep=0pt,itemsep=0pt,topsep=0pt,partopsep=0pt}
    \fixinnerlist{innerlist}

% An environment IDENTICAL to innerlist that has better pre-list spacing
% when used as the first thing in a \section
%
% Usage:
%   \begin{loneinnerlist}
%       \item ...    % (or \item[] for no bullet)
%   \end{loneinnerlist}
\newlist{loneinnerlist}{itemize}{3}
    \setlist[loneinnerlist]{label=\enskip\textbullet,leftmargin=*,parsep=0pt,itemsep=0pt,topsep=0pt,partopsep=0pt}
    \fixendlist{loneinnerlist}
    \fixinnerlist{loneinnerlist}

%%% EXTRA SPACE

% To add some paragraph space between lines.
% This also tells LaTeX to preferably break a page on one of these gaps
% if there is a needed pagebreak nearby.
\newcommand{\blankline}{\quad\pagebreak[3]}
\newcommand{\halfblankline}{\quad\vspace{-0.5\baselineskip}\pagebreak[3]}

%%% FORMATTING MACROS

% Provides a linked \doi{#1} that links doi:#1 to http://dx.doi.org/#1
\usepackage{doi}
% To change the text before the DOI, adjust this command
%\renewcommand\doitext{doi:}

% Provides a linked \url{#1} that doesn't require escape characters
\usepackage{url}

% You can adjust the style \url{} uses here:
% (options are: same, rm, sf, tt; defaults to tt)
\urlstyle{same}

% For \email{ADDRESS}, links ADDRESS to the url mailto:ADDRESS
% (uncomment to typeset the e\-/mail address in typewriter font;
%  otherwise, will be typeset in the \urlstyle above)
%\DeclareUrlCommand\emaillink{\urlstyle{tt}}
\providecommand*\emaillink[1]{\nolinkurl{#1}}
\providecommand*\email[1]{\href{mailto:#1}{\emaillink{#1}}}

\providecommand\BibTeX{{B\kern-.05em{\sc i\kern-.025em b}\kern-.08em \TeX}}
\providecommand\Matlab{\textsc{Matlab}}

% Custom hyphenation rules for words that LaTeX has trouble with
\hyphenation{bio-mim-ic-ry bio-in-spi-ra-tion re-us-a-ble pro-vid-er Media-Wiki}


\newcommand{\cvreference}[7]{%
    \textbf{#1}\newline% Name
    \ifthenelse{\equal{#2}{}}{}{\addresssymbol~#2\newline}%
    \ifthenelse{\equal{#3}{}}{}{#3\newline}%
    \ifthenelse{\equal{#4}{}}{}{#4\newline}%
    \ifthenelse{\equal{#5}{}}{}{#5\newline}%
    \ifthenelse{\equal{#6}{}}{}{\emailsymbol~\texttt{#6}\newline}%
    \ifthenelse{\equal{#7}{}}{}{\phonesymbol~#7}}

%%%%%%%%%%%%%%%%%%%%%%%% End Helper Commands %%%%%%%%%%%%%%%%%%%%%%%%%%%

%%%%%%%%%%%%%%%%%%%%%%%%% Begin CV Document %%%%%%%%%%%%%%%%%%%%%%%%%%%%



\begin{document}
\makeheading{Adam R. Panish}

\section{Contact Information}

% NOTE: Mind where the & separators and \\ breaks are in the following
%       table. Table is one row made up of three parboxes. The left
%       parbox has address info, the middle parbox has a vertical bar,
%       and the right parbox has phone and electronic contact
%       information.
%
% MACROS: \rcollength is the width of the right column of the table
%             (adjust it to your liking; default is 1.85in).
%         \spacewidth is width of area between left and right boxes.
%

\newlength{\rcollength}\setlength{\rcollength}{1.85in}%
\newlength{\spacewidth}\setlength{\spacewidth}{20pt}
%
\begin{tabular}[t]{@{}p{\textwidth-\rcollength-\spacewidth}@{}p{\spacewidth}@{}p{\rcollength}}%

% Address box
\hspace{.16in}
\parbox{\textwidth-\rcollength-\spacewidth}{%
S-753, Social and Behavioral Sciences Building\\
Stony Brook, NY  11794  USA}

&
% Uncomment to add a vertical bar in middle of contact information
%{\vrule width 0.5pt}
\parbox[m][2.5\baselineskip]{\spacewidth}{} &

% Non-snail-mail contact information
\parbox{\rcollength}{%
\email{adam.panish@stonybrook.edu}\\
\href{http://www.adampanish.com/}{www.adampanish.com}}

\end{tabular}

\section{Education}
\vspace{-0.125in}
\begin{outerlist}
\item[] \textbf{Stony Brook University}, Stony Brook, NY
\begin{innerlist}
\item[] Ph.D., Political Science \hfill {2020 - present}
\end{innerlist}
\item[] \textbf{Rutgers University}, New Brunswick, NJ
\begin{innerlist}
\item[] B.A., Political Science \hfill{2019}
\end{innerlist}
\end{outerlist}

% \section{Submitted Journal Publications}
%
% % Add a little space to nudge next ``Ref'd Journal Publications'' marginpar
% % down to make room for tall ``Submitted Journal Publications''
% % marginpar. If there are enough submitted journal publications, this
% % space will not be needed (and should be removed).
% \vspace{0.1in}

\section{Peer-Reviewed Publications}

\begin{bibenum}

    \item[3.] {\bf Panish, A.R.}, and Delton, A.W. \href{https://www.dropbox.com/scl/fi/6asbl7xmwbo2fbpg2q6eq/panish_and_delton_2024.pdf?rlkey=wwmde8r5b71kkw3dkat90zyrc&st=5b11w7q8&dl=0}{Why Anxious People Lean to the Left on Economic Policy: Personality, Social Exclusion, and Redistribution.} Conditionally Accepted at \emph{British Journal of Political Science}

    \item[2.] {\bf Panish, A.R.} and Nam, H.H. (2024). \href{https://doi.org/10.1111/spc3.12916}{The Neurobiology of Political Ideology: Theories, Findings, and Future Directions.} \emph{Social and Personality Psychology Compass, 18}(1), e12916. \doi{10.1111/spc3.12916}

    \item[1.] {\bf Panish, A.R.}, Ludeke, S.G., and Vitriol, J.A. (2023). \href{https://doi.org/10.1111/spc3.12885}{Big five personality and COVID‐19 beliefs, behaviors, and vaccine intentions: The mediating role of political ideology} \textit{Social and Personality Psychology Compass, 17}(12), e12885.\\\doi{10.1111/spc3.12885}

\end{bibenum}


\section{Under Review}
\restartlist{bibenum}

\begin{bibenum}

    \item[] {\bf Panish, A.R.}. Informed or overwhelmed? How cognitive ability shapes the effects of political information. (\emph{Revise \& Resubmit at British Journal of Political Science})
    
    \item[] {\bf Panish, A.R.}, and Feldman, S. Authoritarianism, Redistribution, and Ethnic Diversity. (\emph{under review})
    
\end{bibenum}

\section{In Progress}

\begin{bibenum}

    \item[] {\bf Panish, A.R.}, Delton, A.W., Lukaszewski, A., and Robertson, T.E. Personal Vulnerability and the Moral Politics of Harm. (\emph{data analysis/writing})

    \item[] {\bf Panish, A.R.}, and Delton, A.W. Anger and the Logic of Political Hostility. (\emph{data analysis/writing})
    
    \item[] {\bf Panish, A.R.},  Vitriol, J.A., O'Shea, B.A., and Feldman, S. Infectious disease, authoritarianism, and political behavior: A county-level analysis. (\emph{data collection/analysis})
    
    \item[] {\bf Panish, A.R.} Open Ideologues? How Personality Constrains Legislators' Voting Behavior. (\emph{revisions})

    \item[] Ollerenshaw, T., {\bf Panish, A.R.}, and Vitriol, J.A. The Conditional Associations of Needs for Certinaty and Security with Americans' Responses to COVID-19: Replications and Extensions (\emph{revisions})

\end{bibenum}


\section{Fellowships and Awards}
\restartlist{bibenum}

\begin{bibenum}

    \item[] 2024 Frank Myers Graduate Teaching Award (\$500)
\\\emph{Stony Brook University Department of Political Science}

    \item[] 2023 Milton Lodge Graduate Research Scholarship (\$500)
\\\emph{Stony Brook University Department of Political Science}

    \item[] 2023 Distinguished Travel Award (\$1,372)
\\\emph{Stony Brook University Graduate Student Organization}

    \item[] 2023 APSA Annual Meeting Travel Grant (\$150)
\\\emph{American Political Science Association}

    \item[] 2023 Professional Development Award (\$355)
\\\emph{Stony Brook University Graduate Student Employees Union}

    \item[] 2023 Fine Arts, Humanities, and Social Sciences Grant (\$3,360)
\\\emph{Stony Brook University} (w/ Andrew W. Delton)

    \item[] 2023 Fine Arts, Humanities, and Social Sciences Grant (\$3,500)
\\\emph{Stony Brook University} (w/ Stanley Feldman)

\item[] 2021 Rapoport Summer Collaboration Fellowship (\$4,000)
\\\emph{Rapaport Family Foundation} (w/ Joseph A. Vitriol)

\item[] 2020 Cowart Research and Travel Funds (\$2,000)
\\\emph{Stony Brook University Department of Political Science}

\end{bibenum}

\section{Conference Presentations}

\begin{bibenum}

\item[] \emph{Informed or overwhelmed? How cognitive ability shapes the effects of political information.} Paper Presented at the 81st Annual Meeting of the Midwest Political Science Association, Chicago, IL. April 7, 2024.

\item[] \emph{Authoritarianism, Redistribution, and Ethnic Diversity.} Paper Presented at the 81st Annual Meeting of the Midwest Political Science Association, Chicago, IL. April 5, 2024.

\item[] \emph{Personality, Social Exclusion, and Redistribution: Why Anxious People Lean to the Left on Economic Policy.} Paper presented at the 119th Annual Meeting of the American Political Science Association, Los Angeles, CA. September 10, 2024.

\item[] \emph{How the Interplay of Ability and Information Leads to Stratified Public Opinion.} Paper Presented at the 46th Annual Meeting of the International Society of Political Psychology, Montreal, QC. July 9, 2023.

\item[] \emph{Anxiety, Social Exclusion, and Redistribution: Why Neurotic People Lean to the Left on Economic Policy.} Paper Presented at the 80th Annual Meeting of the Midwest Political Science Association, Chicago, IL. April 14, 2023.

\end{bibenum}

\section{Conference Posters}

\begin{bibenum}

\item[] \emph{Informed or overwhelmed? How cognitive ability shapes the effects of political information.} Poster Presented at the APSA Political Psychology Pre-Conference, Los Angeles, CA. August 30, 2023.

\item[] \emph{The Personality Roots of Redistribution Preferences: Why Neurotic People Support Social Welfare Programs.} Poster Presented at the 2023 Rebecca B. Morton Conference on Experimental Political Science, New York, NY. March 3, 2023

\end{bibenum}

\section{Invited Talks}

\begin{bibenum}
    \item[] \emph{Anxiety, Social Exclusion, and Redistribution} Invited Talk Presented at the Center for Evolutionary Psychology, University of California, Santa Barbara, CA. June 7, 2023

    \item[] \emph{Authoritarianism and Personality.} Invited guest lecture in the Social Sciences Division of Harvard Extension School at Harvard University, Cambridge, MA. February 27, 2023.
 
\end{bibenum}




\section{Teaching Experience}

{\textbf{Stony Brook University}}, Stony Brook, NY
\begin{outerlist}
\item[] \textit{Instructor}
    \begin{innerlist}
        \item POL 201: Intro to Statistical Methods in Political Science \hfill{W23, W24, F24}
        \item POL 344: American Political Ideology and Public Opinion \hfill{F23, Sp24}
    \end{innerlist}
\end{outerlist}

\halfblankline

{\textbf{Harvard University Extension School}}, Cambridge, MA
\begin{outerlist}
\item[] \textit{Teaching Assistant}
    \begin{innerlist}
        \item PSYC E-1587: Fake News and Political Misperceptions \hfill{Sp 2023}
    \end{innerlist}
\end{outerlist}

\section{Professional Service}

\textbf{Reviewer}
\begin{innerlist}
    \item \textit{Politics and the Life Sciences}; \textit{Social and Personality Psychology Compass}
\end{innerlist}

\halfblankline

\textbf{Discussant}
\begin{innerlist}
    \item APSA 2023 (Poster Session: Experimental Research)
\end{innerlist}

\halfblankline

\section{Skills}

\textbf{Languages and Software}: R; Mplus; \LaTeX; Qualtrics
\\\\
\textbf{Data Analysis}: Multilevel models; Tobit/Selection models; Structural equation models (SEM); Item Response Theory (IRT); Multiple imputation (MICE)



\section{References}

\noindent
\begin{tabular}{@{}p{0.5\textwidth} p{0.5\textwidth}@{}}
\textbf{Stanley Feldman, PhD} & \textbf{Andrew W. Delton, PhD} \\
John S. Toll Professor & Associate Professor \\
Department of Political Science & Department of Political Science \\ 
Stony Brook University & College of Business \\
Email: \href{mailto:stanley.feldman@stonybrook.edu}{stanley.feldman@stonybrook.edu} & Stony Brook University \\ 
& Email: \href{mailto:andrew.delton@stonybrook.com}{andrew.delton@stonybrook.com} \\[0.5cm]

\textbf{H. Hannah Nam, PhD} & \textbf{Joseph A. Vitriol, PhD} \\ 
Assistant Professor & Assistant Professor \\
Department of Psychology & Department of Management \\
Brooklyn College & College of Business \\
Email: \href{mailto:hannah.nam@brooklyn.cuny.edu}{hannah.nam@brooklyn.cuny.edu} & Lehigh University \\
& Email: \href{mailto:joevitriol@gmail.com}{joevitriol@gmail.com} 
\end{tabular}


\end{document}

%%%%%%%%%%%%%%%%%%%%%%%%%% End CV Document %%%%%%%%%%%%%%%%%%%%%%%%%%%%%
</math>
