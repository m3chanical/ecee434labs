default: lab1_report.pdf 

%.pdf: %.md Makefile
	pandoc --toc --template=lab_doc.latex --bibliography=references.bib -o $@ $<
clean: 
	rm lab1_report.pdf
