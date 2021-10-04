CC=c:\sandbox\P9\repo\prg_util_toolset\gcc\gcc-x86_64-w64-mingw32-810\bin\g++.exe

CFLAGS=-I../cpp_src -W -Wall -O2 -g -march=native -Ofast \
			-m64 -I../src -mavx2 -mfma \
			-IC:\sandbox\P9\repo\prg_util_toolset\gcc\gcc-x86_64-w64-mingw32-810\lib\gcc\x86_64-w64-mingw32\8.1.0\include\

LDFLAGS=

EXEC=main.exe
#CFLAGS=-Wa,-q -I../cpp_src -W -Wall -ansi -pedantic -O3 -Wall -funroll-loops -ftree-vectorize \
#			-msse4a -march=native -mtune=native -ffast-math -fopenmp \
#			-fstrict-aliasing -fprefetch-loop-arrays -I../src

SRC= \
	../src/CBitGenerator/CBitGenerator.cpp \
	../src/CChanel/CChanel.cpp \
	../src/CChanel/CChanelAWGN_MKL.cpp \
	../src/CDecoder/template/CDecoder.cpp \
	../src/CDecoder/template/CDecoder_fixed.cpp \
	../src/CDecoder/template/CDecoder_fixed_AVX.cpp \
	../src/CDecoder/template/CDecoder_fixed_SSE.cpp \
	../src/CDecoder/OMS/CDecoder_OMS_fixed_SSE.cpp \
	../src/CDecoder/OMS/CDecoder_OMS_fixed_AVX.cpp \
 ../src/CDecoder/NMS/CDecoder_NMS_fixed_SSE.cpp \
 ../src/CDecoder/NMS/CDecoder_NMS_fixed_AVX.cpp \
 ../src/CEncoder/CFakeEncoder.cpp \
 ../src/CEncoder/Encoder.cpp \
 ../src/CEncoder/GenericEncoder.cpp \
 ../src/CErrorAnalyzer/CErrorAnalyzer.cpp \
 ../src/CFixPointConversion/CFastFixConversion.cpp \
 ../src/CFixPointConversion/CFixConversion.cpp \
 ../src/CTerminal/CTerminal.cpp \
 ../src/CTimer/CTimer.cpp \
 ../src/CTools/CTools.cpp \
 ../src/CTools/transpose_avx.cpp \
 ../src/CTrame/CTrame.cpp \
 ../src/main_p.cpp

OBJ= $(SRC:.cpp=.o)

all: $(EXEC)

main.exe: $(OBJ)
	@echo "[LINKING] $@"
	@$(CC) $(CFLAGS) -o $@ $^ $(LDFLAGS)

%.o: %.cpp
	@echo "[C++] $<"
	@$(CC) $(CFLAGS) -o $@ -c $< $(CFLAGS)

.PHONY: clean mrproper

clean:
	cd ../src && del /s *.o && cd ../bin

mrproper: clean
	rm $(EXEC)
