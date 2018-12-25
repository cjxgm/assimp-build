
all:
	mkdir -p build/
	mkdir -p source/
	mkdir -p release/
	curl -L https://github.com/assimp/assimp/archive/v4.0.1.tar.gz | tar xz -C source/ --strip-components 1
	cd build/ && cmake \
		-DCMAKE_BUILD_TYPE=Release \
		-DASSIMP_BUILD_ASSIMP_TOOLS=OFF \
		-DASSIMP_BUILD_TESTS=OFF \
		-DASSIMP_BUILD_ALL_IMPORTERS_BY_DEFAULT=OFF \
		-DASSIMP_BUILD_OBJ_IMPORTER=ON \
		-DASSIMP_BUILD_FBX_IMPORTER=ON \
		-DASSIMP_BUILD_GLTF_IMPORTER=ON \
		../source
	make -C build/ -j8
	find build/ -type f \( -name '*.so' -o -name '*.so.*' -o -name '*.dylib' \) -exec cp -f \{\} release/ \;

