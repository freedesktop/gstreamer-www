NULL = 

ALERTS = \
	sa-2016-0001.xml \
	sa-2016-0002.xml \
	sa-2019-0001.xml \
	sa-2021-0001.xml \
	sa-2021-0002.xml \
	sa-2021-0003.xml \
	sa-2021-0004.xml \
	sa-2021-0005.xml \
	$(NULL)

security_pages = $(patsubst %.xml,%.html,$(ALERTS))


all: index.html $(security_pages)

index.html: index.xml index.xsl alerts.xsl alerts.xml $(top_srcdir)/htdocs/page.xsl
	xsltproc @XSLTPROC_ARGS@ --xinclude $(srcdir)/index.xsl $(srcdir)/index.xml > $@

sa-%.html: $(srcdir)/sa-%.xml $(srcdir)/advisory-detail.xsl $(top_srcdir)/htdocs/page.xsl
	xsltproc @XSLTPROC_ARGS@ $(srcdir)/advisory-detail.xsl $< > $@

built_pages = index.html $(security_pages)

include $(top_srcdir)/html.make

