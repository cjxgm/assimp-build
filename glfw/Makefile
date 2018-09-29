
all:
	mkdir -p build/
	mkdir -p source/
	mkdir -p release/
	curl -L https://github.com/glfw/glfw/archive/3.2.1.tar.gz | tar xz -C source/ --strip-components 1
	cd build/ && cmake \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=ON \
		-DGLFW_BUILD_EXAMPLES=OFF \
		-DGLFW_BUILD_TESTS=OFF \
		-DGLFW_BUILD_DOCS=OFF \
		-DGLFW_INSTALL=OFF \
		../source
	make -C build/ -j8
	find . \( -name '*.so' -o -name '*.so.*' -o -name '*.dylib' \) -exec cp -f \{\} release/ \;

