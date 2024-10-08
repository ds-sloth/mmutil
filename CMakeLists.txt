cmake_minimum_required(VERSION 3.2...3.5)

project(mmutil VERSION 1.10.2 LANGUAGES C)

set(MMUTIL_SRC
	source/adpcm.c
	source/adpcm.h
	source/defs.h
	source/deftypes.h
	source/errors.h
	source/files.c
	source/files.h
	source/gba.c
	source/gba.h
	source/it.c
	source/it.h
	source/kiwi.c
	source/main.c
	source/mas.c
	source/mas.h
	source/mod.c
	source/mod.h
	source/msl.c
	source/msl.h
	source/nds.c
	source/nds.h
	source/poopen.h
	source/s3m.c
	source/s3m.h
	source/samplefix.c
	source/samplefix.h
	source/simple.c
	source/simple.h
	source/solution.h
	source/systems.h
	source/upload.c
	source/version.h
	source/wav.c
	source/wav.h
	source/xm.c
	source/xm.h
	source/arm7_st.inc
	source/arm9_st.inc
)

add_executable(mmutil "${MMUTIL_SRC}")
target_link_libraries(mmutil PRIVATE m)

target_compile_definitions(mmutil PRIVATE "-DPACKAGE_VERSION=\"${CMAKE_PROJECT_VERSION}\"")

if(NOT MSVC)
	target_compile_options(mmutil PRIVATE -Wall -Wextra -Wno-multichar)
endif()
