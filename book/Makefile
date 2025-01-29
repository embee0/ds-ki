# Dies ist ein Makefile. Es wird verwendet, um die Erstellung des Buches 
# zu automatisieren und damit zu vereinfachen.
# Eine Anleitung zur Verwendung von Makefiles findet man z.B. unter
# https://www.jfranken.de/homepages/johannes/vortraege/make.de.html

# Dieses spezielle Makefile ist für die Verwendung mit dem Jupyter-Book
# optimiert. Es bietet folgende Befehle:
# - clean: Löscht alle temporären Dateien und Verzeichnisse
# - build: Baut das Buch in HTML
# - develop: Startet einen lokalen Server und beobachtet Änderungen, d.h.
#   das Buch wird, sobald Änderungen gespeichert werden, neu gebaut und im
#   Browser aktualisiert.
# - publish: Veröffentlicht das Buch online (muss angepasst werden, wenn
#   ein anderer Server verwendet wird)

# Standardziel: Hilfetext anzeigen
all: help


# Startet den Jupyter-Book Server und beobachtet Änderungen, d.h.
# das Buch wird, sobald Änderungen gespeichert werden, neu gebaut
# und im Browser aktualisiert. Man muss nichts weiter tun!!!
develop:
	jupyter-book config sphinx .
	sphinx-autobuild . _build/html -b html --port 0 --open-browser
	# usage: https://pypi.org/project/sphinx-autobuild/0.7.0/

# Löscht alle erzeugten Dateien und Verzeichnisse
clean:
	jupyter-book clean .

# Baut das Buch in HTML
build: clean
	jupyter-book build . --all

# Baut das Buch in HTML aber ohne clean und nur geänderte Dateien 
update: 
	jupyter-book build .

# Buch online veröffentlichen
publish:
	rsync -avz _build/html/* mbqw@carina.uberspace.de:html/tgi13skript/

# Hilfetext
help:
	@echo "Bitte benutze \`make <target>', wobei <target> eines der folgenden ist"
	@echo "  clean       um alle temporären Dateien und Verzeichnisse zu löschen"
	@echo "  build       um das Buch in HTML zu bauen"
	@echo "  develop     um während des Schreibens einen lokalen Server zu starten und Änderungen sofort zu sehen"
	@echo "  publish     um das Buch online zu veröffentlichen."
	@echo "  help        um diese Nachricht anzuzeigen"