.ONESHELL:
.DELETE_ON_ERROR:
export SHELL     := bash
export SHELLOPTS := pipefail:errexit
MAKEFLAGS += --warn-undefined-variables
MAKEFLAGS += --no-builtin-rule

include docs.mk

.PHONY: sources/panels-visualizations/query-transform-data/transform-data/index.md
sources/panels-visualizations/query-transform-data/transform-data/index.md: ## Generate the Transform Data page source.
sources/panels-visualizations/query-transform-data/transform-data/index.md:
	cd $(CURDIR)/..
	npx tsc ./scripts/docs/generate-transformations.ts
	node ./scripts/docs/generate-transformations.js > $(CURDIR)/$@
	npx prettier -w $(CURDIR)/$@
