PATH := ../node_modules/.bin:$(PATH)

SITE_LESS_DIRECTORY = assets/less
SITE_SCSS_DIRECTORY = assets/scss
SITE_CSS_DIRECTORY = assets/css

KB_LESS = ${SITE_LESS_DIRECTORY}/kyruus-bootstrap/kyruus.less
KB_SCSS = ${SITE_SCSS_DIRECTORY}/kyruus-bootstrap/kyruus.scss
KB_CSS = ${SITE_CSS_DIRECTORY}/kyruus.css
KB_CSS_MIN = ${SITE_CSS_DIRECTORY}/kyruus.min.css

DOCS_LESS = ${SITE_LESS_DIRECTORY}/sites/docs.less
DOCS_SCSS = ${SITE_SCSS_DIRECTORY}/sites/docs.scss
DOCS_CSS = ${SITE_CSS_DIRECTORY}/sites/docs.css
DOCS_CSS_MIN = ${SITE_CSS_DIRECTORY}/sites/docs.min.css

build:
	@echo "Compiling Less files"
	@mkdir -p ${SITE_CSS_DIRECTORY}
#	sass ${KB_SCSS}:${KB_CSS}
	lessc ${KB_LESS} > ${KB_CSS}
	lessc --compress ${KB_LESS} > ${KB_CSS_MIN}
	@mkdir -p ${SITE_CSS_DIRECTORY}/sites
#	sass ${DOCS_SCSS}:${DOCS_CSS}
	lessc ${DOCS_LESS} > ${DOCS_CSS}
	lessc --compress ${DOCS_LESS} > ${DOCS_CSS_MIN}


default: build


.PHONY: build
