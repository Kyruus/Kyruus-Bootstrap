PATH := ../node_modules/.bin:$(PATH)

SITE_LESS_DIRECTORY = assets/less
SITE_CSS_DIRECTORY = assets/css

KB_LESS = ${SITE_LESS_DIRECTORY}/kyruus-bootstrap/kyruus.less
KB_CSS = ${SITE_CSS_DIRECTORY}/kyruus.css
KB_CSS_MIN = ${SITE_CSS_DIRECTORY}/kyruus.min.css

DOCS_LESS = ${SITE_LESS_DIRECTORY}/sites/docs.less
DOCS_CSS = ${SITE_CSS_DIRECTORY}/sites/docs.css
DOCS_CSS_MIN = ${SITE_CSS_DIRECTORY}/sites/docs.min.css

build:
	@echo "Compiling Less files"
	@mkdir -p ${SITE_CSS_DIRECTORY}
	lessc ${KB_LESS} > ${KB_CSS}
	lessc --compress ${KB_LESS} > ${KB_CSS_MIN}
	@mkdir -p ${SITE_CSS_DIRECTORY}/sites
	lessc ${DOCS_LESS} > ${DOCS_CSS}
	lessc --compress ${DOCS_LESS} > ${DOCS_CSS_MIN}


default: build


.PHONY: build
