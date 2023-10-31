# You can refer to the base dir of your project if needed with: ${PACKAGE}
PACKAGE := $(shell basename $(CURDIR))

# .PHONY is used so that make will not treat the target as a filename
.PHONY: install test docs clean dist

install:
	python3 -m pip install .

.PHONY: test
test:
	python3 -m pytest test/

# if using Sphinx for docs
docs:
	cd docs;\
	make html

# open the Sphinx docs landing page
opendocs:
	open docs/_build/html/index.html

# clean out dist and build dirs
clean:
	rm -rf dist/* build/*

# build distribution
dist:
	python3 -m build

# upload package to the test pypi site
upload_test:
	python3 -m twine upload --repository-url https://test.pypi.org/legacy/ dist/*

# upload package to pypi
upload:
	python3 -m twine upload dist/*

# both lint cmds assume a requirements-dev.txt with pkg: ruff, isort
lint-fix:
	pip3 install -q -r requirements-dev.txt
	isort .
	ruff check --fix .

lint-check:
	pip3 install -q -r requirements-dev.txt
	isort . --check-only
	ruff check .
