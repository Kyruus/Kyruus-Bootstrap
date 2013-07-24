---
---

PATH := ../node_modules/.bin:$(PATH)

ASSET_DIR = assets
OUTPUT_DIR = ../theme

SITE_LESS_DIR = ${ASSET_DIR}/less
SITE_SCSS_DIR = ${ASSET_DIR}/scss
SITE_CSS_DIR = ${ASSET_DIR}/css

KB_LESS = ${SITE_LESS_DIR}/kyruus-bootstrap/kyruus.less
KB_SCSS = ${SITE_SCSS_DIR}/kyruus-bootstrap/kyruus.scss
KB_CSS = ${SITE_CSS_DIR}/kyruus.css
KB_CSS_MIN = ${SITE_CSS_DIR}/kyruus.min.css

DOCS_LESS = ${SITE_LESS_DIR}/sites/docs.less
DOCS_SCSS = ${SITE_SCSS_DIR}/sites/docs.scss
DOCS_CSS = ${SITE_CSS_DIR}/sites/docs.css
DOCS_CSS_MIN = ${SITE_CSS_DIR}/sites/docs.min.css

build:
	@echo "Making directories"
	@mkdir -p ${SITE_CSS_DIR}
	@mkdir -p ${SITE_CSS_DIR}/sites
	@mkdir -p ${OUTPUT_DIR}

	@echo "Compiling Less files"
#	sass ${KB_SCSS}:${KB_CSS}
	lessc ${KB_LESS} > ${KB_CSS}
	lessc --compress ${KB_LESS} > ${KB_CSS_MIN}
#	sass ${DOCS_SCSS}:${DOCS_CSS}
	lessc ${DOCS_LESS} > ${DOCS_CSS}
	lessc --compress ${DOCS_LESS} > ${DOCS_CSS_MIN}

	@echo "Cleaning old theme"
	rm -rf ${OUTPUT_DIR}/*

	@echo "Copying new theme into place"
	cp -r ${ASSET_DIR}/css ${OUTPUT_DIR}/css
	cp -r ${ASSET_DIR}/font ${OUTPUT_DIR}/font
	cp -r ${ASSET_DIR}/ico ${OUTPUT_DIR}/ico
	@mkdir -p ${OUTPUT_DIR}/img/kyruus-bootstrap
	cp -r ${ASSET_DIR}/img/kyruus-bootstrap ${OUTPUT_DIR}/img
	cp -r ${ASSET_DIR}/js ${OUTPUT_DIR}/js
	cp -r ${ASSET_DIR}/less ${OUTPUT_DIR}/less
	cp -r ${ASSET_DIR}/scss ${OUTPUT_DIR}/scss

	@echo "Cleaning site specific files"
	rm -rf ${OUTPUT_DIR}/css/sites
	rm -rf ${OUTPUT_DIR}/js/sites
	rm -rf ${OUTPUT_DIR}/less/sites
	rm -rf ${OUTPUT_DIR}/scss/sites


default: build


.PHONY: build
