# protocols
Lab protocols from Edward Wallace
Additional protocols by Cat Triandafillou

To convert x.tex to markdown reliably:
htlatex x.tex "xhtml, mathml, charset=utf-8" " -cunihtf -utf8"
pandoc x.html -f html -t markdown
