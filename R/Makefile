PACKAGE := $(shell grep '^Package:' DESCRIPTION | sed -E 's/^Package:[[:space:]]+//')
RSCRIPT = Rscript --no-init-file
FILE_TARGET := "R/${FILE}.R"

# .PHONY is used so that make will not treat the target as a filename
.PHONY: docs test readme

install: doc build
	R CMD INSTALL . && rm *.tar.gz

build:
	R CMD build .

doc:
	${RSCRIPT} -e "devtools::document()"

eg:
	${RSCRIPT} -e "devtools::run_examples(run_dontrun = TRUE)"

check: build
	_R_CHECK_CRAN_INCOMING_=FALSE R CMD CHECK --as-cran --no-manual `ls -1tr ${PACKAGE}*gz | tail -n1`
	@rm -f `ls -1tr ${PACKAGE}*gz | tail -n1`
	@rm -rf ${PACKAGE}.Rcheck

test:
	${RSCRIPT} -e "devtools::test()"

coverage:
	${RSCRIPT} -e 'if (!requireNamespace("covr")) pak::pak("covr")' \
-e 'Sys.setenv(NOT_CRAN = "true"); covr::package_coverage()'

readme:
	${RSCRIPT} -e "knitr::knit('README.Rmd')"

docs:
	${RSCRIPT} -e "pkgdown::build_site(); pkgdown::preview_site(preview=TRUE)"

lint_package:
	${RSCRIPT} -e "lintr::lint_package()"

# use: `make style_file FILE=stuff`
# (`stuff` is put into the string "R/%s.R"); accepts 1 file only
style_file:
	${RSCRIPT} -e 'styler::style_file(${FILE_TARGET})'

style_package:
	${RSCRIPT} -e "styler::style_pkg()"
