
all:
	mkdir -p build/
	mkdir -p source/
	mkdir -p release/
	curl -L https://github.com/nigels-com/glew/releases/download/glew-2.1.0/glew-2.1.0.tgz | tar xz -C source/ --strip-components 1
	cd build/ && cmake \
		-DCMAKE_BUILD_TYPE=Release \
		../source/build/cmake
	make -C build/ -j8 glew
	find . \( -name '*.so' -o -name '*.so.*' -o -name '*.dylib' \) -exec cp -f \{\} release/ \;

