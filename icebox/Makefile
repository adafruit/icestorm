include ../config.mk

all: chipdb-384.txt chipdb-1k.txt chipdb-5k.txt chipdb-8k.txt

chipdb-384.txt: icebox.py iceboxdb.py icebox_chipdb.py
	python3 icebox_chipdb.py -3 > chipdb-384.new
	mv chipdb-384.new chipdb-384.txt

chipdb-1k.txt: icebox.py iceboxdb.py icebox_chipdb.py
	python3 icebox_chipdb.py > chipdb-1k.new
	mv chipdb-1k.new chipdb-1k.txt

chipdb-5k.txt: icebox.py iceboxdb.py icebox_chipdb.py
	python3 icebox_chipdb.py -5 > chipdb-5k.new
	mv chipdb-5k.new chipdb-5k.txt

chipdb-8k.txt: icebox.py iceboxdb.py icebox_chipdb.py
	python3 icebox_chipdb.py -8 > chipdb-8k.new
	mv chipdb-8k.new chipdb-8k.txt

clean:
	rm -f chipdb-1k.txt chipdb-8k.txt chipdb-384.txt chipdb-5k.txt
	rm -f icebox.pyc iceboxdb.pyc

install: all
	mkdir -p $(DESTDIR)$(PREFIX)/share/icebox
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp chipdb-384.txt    $(DESTDIR)$(PREFIX)/share/icebox/
	cp chipdb-1k.txt     $(DESTDIR)$(PREFIX)/share/icebox/
	cp chipdb-8k.txt     $(DESTDIR)$(PREFIX)/share/icebox/
	cp icebox.py         $(DESTDIR)$(PREFIX)/bin/icebox.py
	cp iceboxdb.py       $(DESTDIR)$(PREFIX)/bin/iceboxdb.py
	cp icebox_chipdb.py  $(DESTDIR)$(PREFIX)/bin/icebox_chipdb
	cp icebox_diff.py    $(DESTDIR)$(PREFIX)/bin/icebox_diff
	cp icebox_explain.py $(DESTDIR)$(PREFIX)/bin/icebox_explain
	cp icebox_colbuf.py  $(DESTDIR)$(PREFIX)/bin/icebox_colbuf
	cp icebox_html.py    $(DESTDIR)$(PREFIX)/bin/icebox_html
	cp icebox_maps.py    $(DESTDIR)$(PREFIX)/bin/icebox_maps
	cp icebox_vlog.py    $(DESTDIR)$(PREFIX)/bin/icebox_vlog
	cp icebox_stat.py    $(DESTDIR)$(PREFIX)/bin/icebox_stat

uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox.py
	rm -f $(DESTDIR)$(PREFIX)/bin/iceboxdb.py
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_chipdb
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_diff
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_explain
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_colbuf
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_html
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_maps
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_vlog
	rm -f $(DESTDIR)$(PREFIX)/bin/icebox_stat
	rm -f $(DESTDIR)$(PREFIX)/share/icebox/chipdb-384.txt
	rm -f $(DESTDIR)$(PREFIX)/share/icebox/chipdb-1k.txt
	rm -f $(DESTDIR)$(PREFIX)/share/icebox/chipdb-8k.txt
	-rmdir $(DESTDIR)$(PREFIX)/share/icebox

.PHONY: all clean install uninstall
