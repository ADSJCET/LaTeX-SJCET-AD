<b><h1 align="center"> Citing with BIBTEX </h1></b>

*A citation (or reference) uniquely identifies a source of information, it usually has two parts. In the first part, each section of text that is either based on, or quoted from, an outside source is marked as such with an `inline citation`. This is usually displayed as a superscript footnote number: [1]. The second necessary part of the citation or reference is the `list of full references`, which provides complete, formatted detail about the source, so that anyone reading the article can find it and verify it. -- From [Wikipedia](https://en.wikipedia.org/wiki/Wikipedia:Citing_sources)*

While giving citation we have two methods:
1. Giving the citation manually by writing the number and the list of references in a specific format, It is recommended only for very short articles as it need heavy manual work if you need to insert some citation in between other citations, This site was followed in [Mini Project Template](https://github.com/ADSJCET/LaTeX-SJCET-AD/blob/main/src/ref.tex).
2. Giving the citation with automatic numbering using Bibtex. This method is followed in [Main Project Template(Phase 2) CHANGE LINK](https://github.com/ADSJCET/LaTeX-SJCET-AD/blob/main/src/ref.tex). We are discussing this method here.

## Process

In our templates, you have to add the below lines, to ref.tex or similar-named file to make it work with BIBTEX Citation.

```
\bibliographystyle{IEEEtran} # IEEE Transactions bibliography style
\bibliography{ref} # ref is the name of .bib file
```
Then go for

1. Make a .bib file in your project folder (example: `ref.bib`)
2. Get a BIBTEX text from digital libraries like
   * [IEEE Xplore](https://ieeexplore.ieee.org/Xplore/home.jsp) (Near the bold heading, click `Cite This` -> select `BibTeX` -> Copy or Download)
   * [arXiv](https://arxiv.org/) (On the RHS of landing page of a paper -> See the links, look and click `Export BibTeX Citation` -> Copy)
   * Most public works(Research Papers, Codes) has citation option, no matter if it is behind a paywall.
     
A typical BIBTEX look like this (Paper: Attention Is All You Need, Introduced Transformer Model)
```
@misc{vaswani2023attention,
      title={Attention Is All You Need}, 
      author={Ashish Vaswani and Noam Shazeer and Niki Parmar and Jakob Uszkoreit and Llion Jones and Aidan N. Gomez and Lukasz Kaiser and Illia Polosukhin},
      year={2023},
      eprint={1706.03762},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

3. Paste the BIBTEX on your `.bib` file.
4. On the first line of your BIBTEX(here `@misc{vaswani2023attention,`) you may change the `vaswani2023attention` to a name you like to call the paper, eg: `transf_paper`. 
5. Go to you main document TeX file, like chapter.tex or thesis.tex and type `\cite{<your_paper_name>}`(here `\cite{transf_paper}`) to cite the paper in your document.
6. See example at [Main Project Chapter 1, line 116 CHANGE LINK](https://ieeexplore.ieee.org/Xplore/home.jsp)
7. After re-building the project, you will see the citation and list of references like you see in Research Papers.

NOTE: 
* BIBTEX number the paper and add to references only if you add the paper using \cite{} command.
* LaTeX doesn't count/display the BIBTEXes that are added to .bib file, unless you call the paper to you document.
* Ordered numbering will be done by LaTeX itself, you just give name to the ref paper and call it.
