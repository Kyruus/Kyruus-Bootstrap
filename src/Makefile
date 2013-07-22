PATH := ../node_modules/.bin:$(PATH)

KB_LESS_DIRECTORY = assets/less/kyruus-bootstrap
KB_CSS_DIRECTORY = assets/css/

KB_LESS = ${KB_LESS_DIRECTORY}/kyruus.less
KB_CSS = ${KB_CSS_DIRECTORY}/kyruus.css
KB_CSS_MIN = ${KB_CSS_DIRECTORY}/kyruus.min.css

build:
	@echo "Compiling Less files"
	@mkdir -p ${KB_CSS_DIRECTORY}
	lessc ${KB_LESS} > ${KB_CSS}
	lessc --compress ${KB_LESS} > ${KB_CSS_MIN}


default: build


.PHONY: build
