EXECUTABLE = arap_mesh_deformation
OBJS = build/LandMark.o build/LandMarkSet.o build/CUDAWarpingSolver.o build/mLibSource.o build/main.o build/WarpingSolver.o

UNAME := $(shell uname)
ifeq ($(UNAME), Darwin)
  LFLAGS += -L../external/OpenMesh/lib/osx -Wl,-rpath,../external/OpenMesh/lib/osx
endif

ifeq ($(UNAME), Linux)
  LFLAGS += -L/home/mihai/Downloads/OpenMesh-6.3/build/Build/lib -Wl,-rpath,/home/mihai/Downloads/OpenMesh-6.3/build/Build/lib -DOM_STATIC_BUILD
endif

LFLAGS += -lOpenMeshCore -lOpenMeshTools

include ../shared/make_template.inc
