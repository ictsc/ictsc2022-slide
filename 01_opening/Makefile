serve: ictsc.css
	npx -y @marp-team/marp-cli@latest --theme ictsc.css --allow-local-files -s .


dist.md:
	echo "---" > dist.md
	echo "marp: true" >> dist.md
	echo "theme: ictsc" >> dist.md
	echo "paginate: true" >> dist.md
	cat *.md | grep -v "marp:" | grep -v "theme:" | grep -v "paginate" | uniq >> dist.md

dist.pdf: ictsc.css dist.md
	npx -y @marp-team/marp-cli@latest dist.md --pdf --theme ictsc.css --allow-local-files dist.pdf


dist.html: ictsc.css dist.md
	npx -y @marp-team/marp-cli@latest dist.md --theme ictsc.css --allow-local-files dist.html

dist.pptx: ictsc.css dist.md
	npx -y @marp-team/marp-cli@latest dist.md --pptx --theme ictsc.css --allow-local-files dist.pptx

ictsc.css:
	wget https://raw.githubusercontent.com/ictsc/marp-ictsc-theme/main/theme/ictsc.css
	
clean:
	rm -rf dist.*
