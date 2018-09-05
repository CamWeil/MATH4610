Homework 1

%==================================================================
% Cut and paste the following 29 lines into the top of your quiz file.  
% Remember to uncomment the \end{document} statement at the bottom.
%==================================================================
\documentclass[10pt,twoside,reqno]{article}
\usepackage[marginparsep=1em]{geometry}
\geometry{lmargin=1.0in,rmargin=1.0in, bmargin=0.75in,  tmargin=0.75in}
\usepackage[usenames,dvipsnames,svgnames,table]{xcolor}
\usepackage{graphicx}
\usepackage{amssymb}
\usepackage{epstopdf}
\usepackage{tikz}
\usepackage{enumerate}
\usepackage{amsthm}
 \usepackage{pgfplots}
 \usepackage{tikz-3dplot}
 \usetikzlibrary{shapes.geometric}
 \usepackage{float}
\usepackage{amsmath}
\usepackage{fancyhdr}
\usepackage{lmodern}
\usepackage{chngcntr}
\usepackage{multicol, comment}
\usepackage{enumitem}
\graphicspath{{/Users/Platinum/Desktop/}}

\pagestyle{fancy}
\fancyhf{}
\renewcommand{\sectionmark}[1]{\markright{\thesection.\ #1}}
\lhead{\fancyplain{}{}} 
\fancyhead[RE,RO]{MATH 4610}
\fancyhead[LE,LO]{Cam Weil: A01976854}
\fancyfoot[LE,RO]{\thepage}

\begin{document}
\center{Homework 1}

\begin{enumerate}
\item [Problem:] We will use Taylor series expansions in a lot of the work we do in Math 4610. Expand the following functions about the given center $x_0$. Find the radius of convergence of each series.
	\begin{enumerate}
	\item [a.] $f(x) = \sin(2x)$ and $x_0 = 0$
	\item [b.] $f(x) = \ln(2x)$ and $x_0 = 1$
	\item [c.] $f(x) = e^{2x}$ and $x_0 = 1$
	\item [d.] $f(x) = 3x^2 - 2x + 5$ and $x_0 = 0$
	\item [e.] $f(x) = 3x^2 - 2x + 5$ and $x_0 = 1$
	\item [f.] $f(x) = (3x^2 - 2x + 5)^{-1}$ and $x_0 = 1$
	\item [g.] $f(x) = \cosh(x - 3)$ and $x_0 = 1$
	\item [h.] $f(x)$ and $x_0 = a$
	\item [i.] $f(a)$ and $x_0 = x$
	\item [j.] $f(a + h)$ and $x_0 = a$
	\end{enumerate}
	
\item [Solution:] $f(x) = \sum_{n = 0}^{\infty} \frac{f^{(n)}(x_0)}{n!}(x - x_0)^n = f(x_0) + f'(x_0)(x - x_0) + \frac{f''(x_0)}{2!}(x - x_0)^2 + \frac{f'''(x_0)}{3!}(x - x_0)^3 + \cdots$
	\begin{enumerate}
	\item [a.] $\sin(2x) = \sum_{n = 0}^{\infty} (-1)^n \frac{(2x)^{2n + 1}}{(2n + 1)!} = (2x) - \frac{(2x)^3}{3!} + \frac{(2x)^5}{5!} - \frac{(2x)^7}{7!} + \cdots = 2x - \frac{8x^3}{3!} + \frac{32x^5}{5!} - \frac{128x^7}{7!} + \cdots$ \\
	$L = \lim_{n \to \infty} |[(-1)^{n + 1} \frac{(2x)^{2(n + 1) + 1}}{(2(n + 1) + 1)!}][\frac{1}{(-1)^n} \frac{(2n + 1)!}{(2x)^{2n + 1}}]| = \lim_{n \to \infty} |(-1)[\frac{(2x)^{2n + 3}}{(2n + 3)!}][\frac{(2n + 1)!}{(2x)^{2n + 1}}]| = \lim_{n \to \infty}$ \\ $|\frac{(2x)^2}{(2n + 3)(2n + 2)}| = |4x^2| \lim_{n \to \infty} \frac{1}{4n^2 + 10n + 6}$, where the series converges if $L < 1$. This occurs regardless of $x$, so the radius of convergence of the series is $-\infty < x < \infty$.
	\item [b.] $\ln(2x) = \ln(2) + \sum_{n = 1}^{\infty} (-1)^{n + 1}\frac{(x - 1)^n}{n} = \ln(2) + (x - 1) - \frac{(x - 1)^2}{2} + \frac{(x - 1)^3}{3} - \frac{(x - 1)^4}{4} + \cdots$ \\
	$L = \lim_{n \to \infty} |[(-1)^{(n + 1) + 1}\frac{(x - 1)^{n + 1}}{n + 1}][\frac{1}{(-1)^{n + 1}}\frac{n}{(x - 1)^n}]| = \lim_{n \to \infty} |(-1)\frac{n(x - 1)}{n + 1}| = |x - 1| \lim_{n \to \infty} \frac{n}{n + 1}$, where the series converges if $L < 1$. This occurs when $-1 < x - 1 < 1$, so the radius of convergence of the series is $0 < x \leq 2$.
	\item [c.] $e^{2x} = \sum_{n = 0}^{\infty} 2^ne^2\frac{(x - 1)^n}{n!} = e^2 + 2e^2(x - 1) + \frac{2^2e^2}{2!}(x - 1)^2 + \frac{2^3e^2}{3!}(x - 1)^3 + \cdots$ \\
	$L =  \lim_{n \to \infty} |[2^{n + 1}e^2\frac{(x - 1)^{n + 1}}{(n + 1)!}][\frac{1}{2^ne^2}\frac{n!}{(x - 1)^n}]| = \lim_{n \to \infty} |2\frac{(x - 1)}{(n + 1)}| = |2x - 2| \lim_{n \to \infty} \frac{1}{n + 1}$, where the series converges if $L < 1$. This occurs regardless of $x$, so the radius of convergence of the series is $-\infty < x < \infty$.
	\item [d.] $f(x) = [3(0)^2 - 2(0) + 5] + [6(0) - 2](x) + [\frac{6}{2!}](x)^2 = 5 - 2x + 3x^2$. $f(x)$ has a finite number of terms, so the radius of convergence of the series is $-\infty < x < \infty$.
	\item [e.] $f(x) = [3(1)^2 - 2(1) + 5] + [6(1) - 2](x - 1) + [\frac{6}{2!}](x - 1)^2 = 6 + 4(x - 1) + 3(x^2 - 2x + 1) = 6 + 4x - 4 + 3x^2 - 6x + 3 = 5 - 2x + 3x^2$. $f(x)$ has a finite number of terms, so the radius of convergence of the series is $-\infty < x < \infty$.
	\item [f.] $f(x) = \frac{1}{3(1)^2 - 2(1) + 5} + \frac{-6(1) + 2}{[3(1)^2 - 2(1) + 5]^2}(x - 1) + \cdots = \frac{1}{6} + \frac{-4}{36}(x - 1) + \cdots = \frac{1}{6} - \frac{x - 1}{9} + \cdots$
	\item [g.] $\cosh(x - 3) = \sum_{n = 0}^{\infty} \cosh(2)\frac{(x - 1)^{2n}}{(2n)!} - \sum_{n = 0}^{\infty} \sinh(2)\frac{(x - 1)^{2n + 1}}{(2n + 1)!} = \cosh(2) - \sinh(2)(x - 1) + \frac{\cosh(2)}{2!}(x - 1)^2 - \frac{\sinh(2)}{3!}(x - 1)^3 + \cdots$ \\
	$L = \lim_{n \to \infty} |[\cosh(2)\frac{(x - 1)^{2(n + 1)}}{(2(n + 1))!}][\frac{1}{\cosh(2)}\frac{(2n)!}{(x - 1)^{2n}}]| = \lim_{n \to \infty} |[\frac{(x - 1)^{2n + 2}}{(2n + 2)!}][\frac{(2n)!}{(x - 1)^{2n}}]| = \lim_{n \to \infty}$ \\ $|\frac{(x - 1)^2}{(2n + 2)(2n + 1)}| = |x^2 - 2x + 1| \lim_{n \to \infty} \frac{1}{4n^2 + 5n + 2}$, where the series converges if $L < 1$. This occurs regardless of $x$, so the first portion of the series is convergent. \\
	$L = \lim_{n \to \infty} |[\sinh(2)\frac{(x - 1)^{2(n + 1) + 1}}{(2(n + 1) + 1)!}][\frac{1}{\sinh(2)}\frac{(2n + 1)!}{(x - 1)^{2n + 1}}]| = \lim_{n \to \infty} |[\frac{(x - 1)^{2n + 3}}{(2n + 3)!}][\frac{(2n + 1)!}{(x - 1)^{2n + 1}}]| = \lim_{n \to \infty}$ \\ $|\frac{(x - 1)^2}{(2n + 3)(2n + 2)}| = |x^2 - 2x + 1| \lim_{n \to \infty} \frac{1}{4n^2 + 10n + 6}$, where the series converges if $L < 1$. This occurs regardless of $x$, so the second portion of the series is convergence. \\
	Since the sum of two convergent series is also convergent, then the radius of convergence of the entire series is $-\infty < x < \infty$.
	\item [h.] $f(x) = f(a) + f'(a)(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f'''(a)}{3!}(x - a)^3 + \cdots$
	\item [i.] $f(a) = f(x) + f'(x)(a - x) + \frac{f''(x)}{2!}(a - x)^2 + \frac{f'''(x)}{3!}(a - x)^3 + \cdots$
	\item [j.] $f(a + h) = f(a) + f'(a)(a + h - a) + \frac{f''(a)}{2!}(a + h - a) + \frac{f'''(a)}{3!}(a + h - a) + \cdots = f(a) + hf'(a) + \frac{hf''(a)}{2!} + \frac{hf'''(a)}{3!} + \cdots$
	\end{enumerate}

\item [Problem:] Compute the following antiderivatives.
	\begin{enumerate}
	\item [a.] $\int x \sin(2x) dx$ (by parts)
	\item [b.] $\int x e^{x^2} dx$ (by substitution)
	\item [c.] $\int x e^x dx$ (by parts)
	\item [d.] $\int e^{x^2} dx$ (expand integrand in a Taylor series)
	\item [e.] $\int x \sqrt{1 + x} dx$
	\item [f.] $\int \sec(\theta) d\theta$
	\item [g.] $\int \sec^2(\theta) d\theta$
	\item [h.] $\int$ sech$^2(\theta) d\theta$
	\item [i.] $\int \frac{x^2 + 2}{7 - x^2} dx$
	\item [j.] $\int \frac{1}{ap - bp^2} dp$
	\end{enumerate}
	
\item [Solution:]
	\begin{enumerate}
	\item [a.] $u = x, \quad dv = \sin(2x) dx, \quad du = dx, \quad v = -\frac{\cos(2x)}{2}
	\quad \to \quad
	\int u dv = uv - \int v du$ \\
	$\int x \sin(2x) dx = -\frac{x\cos(2x)}{2} + \int \frac{\cos(2x)}{2}dx = -\frac{x\cos(2x)}{2} + \frac{\sin(2x)}{4} + C = \frac{\sin(2x) - 2x\cos(2x)}{4} + C$
	\item [b.] $u = e^{x^2}, \quad du = 2xe^{x^2} dx
	\quad \to \quad
	\int xe^{x^2} dx = \int \frac{1}{2} du = \frac{u}{2} + C = \frac{e^{x^2}}{2} + C$
	\item [c.] $u = x, \quad dv = e^x dx, \quad du = dx, \quad v = e^x 
	\quad \to \quad 
	\int u dv = uv - \int v du$ \\
	$\int xe^x dx = xe^x - \int e^x dx = xe^x - e^x + C = e^x(x - 1) + C$
	\item [d.] $e^x = \sum_{n = 0}^{\infty} \frac{x^n}{n!} = 1 + x^ + \frac{x^2}{2!} + \frac{x^3}{3!} + \cdots
	\quad \to \quad 
	e^{x^2} = \sum_{n = 0}^{\infty} \frac{x^{2n}}{n!} = 1 + x^2 + \frac{x^4}{2!} + \frac{x^6}{3!} + \cdots$ \\
	$\int e^{x^2} dx = \int (1 + x^2 + \frac{x^4}{2!} + \frac{x^6}{3!} + \cdots) dx = x + \frac{x^3}{3} + \frac{x^5}{5(2!)} + \frac{x^7}{7(3!)} + \cdots + C$
	\item [e.] $u = 1 + x, \quad du = dx
	\quad \to \quad
	\int x\sqrt{1 + x} dx = \int (u - 1)\sqrt{u} du = \int u^{3/2} - \sqrt{u} du = \frac{2u^{5/2}}{5} - \frac{2u^{3/2}}{3} + C$ \\
	$\int x\sqrt{1 + x} dx = \frac{2(1 + x)^{5/2}}{5} - \frac{2(1 + x)^{3/2}}{3} + C = \frac{6(1 + x)^{5/2} - 10(1 + x)^{3/2}}{15} + C = \frac{(1 + x)^{3/2}(6x - 4)}{15} + C$
	\item [f.] $\int \sec(\theta) d\theta = \int \frac{\sec(\theta)\tan(\theta) + \sec^2(\theta)}{\tan(\theta) + \sec(\theta)} d\theta
	\quad \to \quad
	u = \tan(\theta) + \sec(\theta), \quad du = \sec(\theta)\tan(\theta) + \sec^2(\theta) d\theta$ \\
	$\int \sec(\theta) d\theta = \int \frac{1}{u} du = \ln(u) + C = \ln(\tan(\theta) + \sec(\theta)) + C = \ln|\tan(\theta) + \sec(\theta)| + C$
	\item [g.] $\int \sec^2(\theta) d\theta = \tan(\theta) + C$
	\item [h.] $\int$ sech$^2(\theta) d\theta = \tanh(\theta) + C$
	\item [i.] $\int \frac{x^2 + 2}{7 - x^2} dx = -\int \frac{x^2 + 2}{x^2 - 7} dx = -\int \frac{x^2 - 7}{x^2 - 7} + \frac{9}{x^2 - 7} dx = -\int \frac{9}{x^2 - 7} + 1 dx = -\int \frac{9}{(x - \sqrt{7})(x + \sqrt{7})} dx + 1 dx$ \\
	$\int \frac{x^2 + 2}{7 - x^2} dx = -9\int \frac{A}{x - \sqrt{7}} + \frac{B}{x + \sqrt{7}} dx - \int 1 dx = -9\int \frac{Ax + \sqrt{7}A + Bx - \sqrt{7}B}{(x - \sqrt{7})(x + \sqrt{7})} dx - x + C$ \\
	$\int \frac{x^2 + 2}{7 - x^2} dx = - 9[\int \frac{1}{2\sqrt{7}(x - \sqrt{7})} dx - \int \frac{1}{2\sqrt{7}(x + \sqrt{7})} dx] - x + C = -9[\frac{\ln(x - \sqrt{7})}{2\sqrt{7}} - \frac{\ln(x + \sqrt{7})}{2\sqrt{7}}] - x + C$ \\
	$\int \frac{x^2 + 2}{7 - x^2} dx = -\frac{9(\ln|x - \sqrt{7}| - \ln|x + \sqrt{7}|)}{2\sqrt{7}} - x + C = \frac{9(\ln|x + \sqrt{7}| - \ln|x - \sqrt{7}|)}{2\sqrt{7}} - x + C$
	\item [j.] $\int \frac{1}{ap - bp^2} dp = -\int \frac{1}{bp^2 - ap} dp = - \int \frac{1}{(b - a/p)p^2} dp
	\quad \to \quad
	u = b - \frac{a}{p}, \quad du = \frac{a}{p^2} dp$ \\
	$\int \frac{1}{ap - bp^2} dp = -\int \frac{1}{au} du = -\frac{\ln(u)}{a} + C = -\frac{\ln(b - a/p)}{a} + C = -\frac{\ln|a/p - b|}{a} + C$
	\end{enumerate}

\item [Problem:] Compute the solutions for the following simple initial value problems.
	\begin{enumerate}
	\item [a.] $\frac{dx}{dt} = 3x$ and $x(0) = 1.0$
	\item [b.] $\frac{dx}{dt} = 3tx$ and $x(0) = 1.0$
	\item [c.] $\frac{dx}{dt} = 0.1x - 0.003x^2$ and $x(0) = 4$
	\item [d.] $\frac{dx}{dt} = 0.1x - 0.003x^2$ and $x(0) = 400$
	\end{enumerate}

\item [Solution:]
	\begin{enumerate}
	\item [a.] $\frac{dx}{dt} = 3x
	\quad \to \quad
	\frac{dx}{dt} - 3x = 0
	\quad \to \quad
	r - 3 = 0
	\quad \to \quad
	r = 3$ \\
	$x(t) = c_1e^{3t}
	\quad \to \quad
	x(0) = c_1 = 1
	\quad \to \quad
	x(t) = e^{3t}$
	\item [b.] $\frac{dx}{dt} = 3tx
	\quad \to \quad
	\frac{dx}{x} = 3t dt
	\quad \to \quad
	\int \frac{dx}{x} = \int 3t dt
	\quad \to \quad
	\ln(x) = \frac{3t^2}{2} + c_1$ \\
	$x(t) = c_1e^{3t^2/2}
	\quad \to \quad
	x(0) = c_1 = 1
	\quad \to \quad
	x(t) = e^{3t^2/2}$
	\item [c.] $\frac{dx}{dt} = 0.1x - 0.003x^2
	\quad \to \quad
	x^{-2}\frac{dx}{dt} = 0.1x^{-1} - 0.003
	\quad \to \quad
	v = x^{-1}
	\quad \to \quad
	\frac{dv}{dt} = -x^{-2}\frac{dx}{dt}$ \\
	$-\frac{dv}{dt} = 0.1v - 0.003
	\quad \to \quad
	\frac{dv}{dt} + 0.1v = 0.003
	\quad \to \quad
	\mu = e^{\int 0.1 dt} = e^{0.1t}$ \\
	$e^{0.1t}\frac{dv}{dt}' + 0.1e^{0.1t}v = 0.003e^{0.1t}
	\quad \to \quad
	\frac{d}{dt}(e^{0.1t}v) = 0.003e^{0.1t}
	\quad \to \quad
	e^{0.1t}v = \int 0.003e^{0.1t} dt$ \\
	$v = 0.03e^{-0.1t}e^{0.1t} + c_1e^{-0.1t}
	\quad \to \quad
	x^{-1} = 0.03 + c_1e^{-0.1t}
	\quad \to \quad
	x(t) = \frac{1}{0.03 + c_1e^{-0.1t}}$ \\
	$x(0) = \frac{1}{0.03 + c_1} = 4
	\quad \to \quad
	0.12 + 4c_1 = 1
	\quad \to \quad
	c_1 = 0.22
	\quad \to \quad
	x(t) = \frac{1}{0.03 + 0.22e^{-0.1t}}$
	\item [d.] $x(0) = \frac{1}{0.03 + c_1} = 400
	\quad \to \quad
	12 + 400c_1 = 1
	\quad \to \quad
	c_1 = -0.0275
	\quad \to \quad
	x(t) = \frac{1}{0.03 - 0.0275e^{-0.1t}}$
	\end{enumerate}

\item [Problem:] Graph the solutions of the last two differential equations in the Problem above. That is:
	\begin{enumerate}
	\item [a.] $\frac{dx}{dt} = 0.1x - 0.003x^2$ and $x(0) = 4$
	\item [b.] $\frac{dx}{dt} = 0.1x - 0.003x^2$ and $x(0) = 400$
	\end{enumerate}
You do not need to recompute the solutions. Just graph them.

\item [Solution:]
	\begin{enumerate}
	\item [a.] 
	\item [] \begin{figure}[H]
\includegraphics[width = 500pt]{1}
\centering
\end{figure}
	\item [b.] 
	\item [] \begin{figure}[H]
\includegraphics[width = 500pt]{2}
\centering
\end{figure}
	\end{enumerate}
	
\end{enumerate}

\end{document}  
