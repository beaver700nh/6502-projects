.PHONY: all
all: build

.PHONY: build
build:
	(mkdir -p build; cd build; cmake ..; make -j4)

.PHONY: clean
clean:
	rm -r build
