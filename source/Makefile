YAML_FILES=$(shell find . -iname '*.yml')
JSON_FILES=$(patsubst %.yml,%.json,$(YAML_FILES))

all: $(JSON_FILES) HAS_YAML2JSON

%.json: %.yml
	yaml2json $< > $@

HAS_YAML2JSON:
	@if ! command -v yaml2json > /dev/null; then            \
	    echo 'Error: need "npm install yaml-to-json"' 1>&2; \
	    exit 1;                                             \
	fi
