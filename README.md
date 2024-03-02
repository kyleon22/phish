# catch-the-phish-ML
this project utilizes machine learning to categorize URLs as phishing or benign

This project takes into consideration a number of features that could indicate the phishing nature of a URL/domain.
Features taken into consideration included address bar features, HTML features as well as Domain related features.
As contained in the code, the various functions shall be touched.

It is important to understand the structure of a legitimate URL so as to put in context some of the features that 
were extracted for the project.

**http://www.example.com:80/file.html?someting=value1=value2#fragment**

http - protocol
www - subdomain
example.com - domain
80 - port number. This could be anything. 80 was only used for the purpose of illustration
file.html - this is the file to be accessed
something = value1 = value2 - this is the query part of the url and it usually comes after the '?'.
fragment -  this is the part that comes after the '#'

***Address Bar Features***

**Presence of '@' in URL**
From the URL structure depicted above, it can be seen that the inclusion of the '@' sign in the URL 
is a rare occurence. Usually the address bar ignores anything that comes before the '@' sign, hence
an attacker could decide to trick an unsuspecting user into believing they are visiting a genuine website.

**Presence of '*' in URL**
The explanation for this holds like for the previous.

**Presence of '$' in URL**
This is also a lexical misnoma which rarely occurs in legitimate URLs. This is not to say legitimate URLs do 
not contain some of these characters. They are rare occurences though, which explains the reason for false positives
when using machine learning for classification as in this case.

**Presence of '|' in URL**
The explanation for the previous characters holds for this as well.

**Position of the tld in a url**
This is another way attackers spoof URL lexicon to mislead unsuspecting users. take ro example
http://example.com/file.html@hacker.com
the actual website the user will be directed to is hacker.com, not example.com. This code searches for tlds that are
wrongly placed.

**Presence of '//' within the URL path**
This is another way that hackers / attackers use to decieve users into visiting dangerous websites where their credentials 
can be compromised.

**Typosquatting**
This is an important feature which is commonly used bt attackers. a typical example is www.g00gle.com. this could pass for
www.google.com, but in the real sense, they are not the same. features based of typosquating were also extracted for the project.

**URL shortening**
Again, this can be a legitimate practice, but is has equally been adopted by attackers to mislead users. 





