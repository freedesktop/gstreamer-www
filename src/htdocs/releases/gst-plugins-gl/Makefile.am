releases = 0.10.3 0.10.2 0.10.1

built_pages = \
	$(releases) \
	$(releases:=.html)

style = ../releases.xsl

$(built_pages): $(style) ../text.xsl

%: %.xml
	xsltproc @XSLTPROC_ARGS@ -o $@ $(srcdir)/../text.xsl $<

include $(top_srcdir)/html.make
