---
title: "An Efficient Framework for Supporting Nested Transaction in STM"
collection: publications
category: conferences
permalink: https://link.springer.com/chapter/10.1007/978-3-031-67321-4_13
excerpt: 'This paper is about developing an effoecient framework for STM which supports nested transactions.'
date: 2024-04-22
venue: 'NETYS, Rabat, Morocco'
# paperurl: 'http://academicpages.github.io/files/paper3.pdf'
# citation: 'Your Name, You. (2024). &quot;Paper Title Number 3.&quot; <i>GitHub Journal of Bugs</i>. 1(3).'
# citation: 'Nischay Ranjan, Rohit Kapoor, and Sathya Peri. (2024). "An Efficient Framework for Supporting Nested Transaction in STMs." In <i>Networked Systems</i>, edited by Armando Castañeda, Constantin Enea, and Nirupam Gupta, pp. 204-210. Springer Nature Switzerland. DOI: [10.1007/978-3-031-67321-4_13](https://doi.org/10.1007/978-3-031-67321-4_13).'
# <a href="https://doi.org/10.1007/978-3-031-67321-4_13" class="btn" target="_blank" rel="noopener noreferrer">DOI</a>
# <a href="C:\Users\Nischay\OneDrive - IIT Hyderabad\Desktop\Website (portfolio)\ranjannischay.github.io\_publications\bibtex_netys2024.bib" class="btn" download>Download BibTeX</a>



---


<!-- The contents above will be part of a list of publications, if the user clicks the link for the publication than the contents of section will be rendered as a full page, allowing you to provide more information about the paper for the reader. When publications are displayed as a single page, the contents of the above "citation" field will automatically be included below this section in a smaller font. -->

Software Transactional Memory (STM) offers a promising avenue for simplifying the intricacies associated with concurrent programming. However, for an STM system to be truly effective, it must accommodate nesting, which will achieve composability and mitigate the extended vulnerability period associated with prolonged transactions. So far, a few protocols have been proposed for the nested STM system that supports nonlinear closed nesting. Either they do not provide any experimental evaluation of their protocol or provide concrete arguments for satisfying opacity, i.e., correctness criteria for the STM system. This paper introduces NestedBTO, an STM protocol tailored for closed nested transactions. Our protocol facilitates the parallel execution of child transactions and is based on timestamp ordering for transactions. Through extensive experimental evaluations, we observe a significant performance improvement compared to flat nesting and serial scheduling in microbenchmark scenarios involving a counter and hashtable. These findings underscore the efficacy of our implementation in optimizing transactional operations within the STM framework.
<a href="https://doi.org/10.1007/978-3-031-67321-4_13" class="btn" target="_blank" rel="noopener noreferrer">DOI</a>
<a href="C:\Users\Nischay\OneDrive - IIT Hyderabad\Desktop\Website (portfolio)\ranjannischay.github.io\_publications\bibtex_netys2024.bib" class="btn" download>Download BibTeX</a>
