TARGETS="${TARGETS:=X86;AMDGPU;BPF}" &&

OPTS+=" -DLLVM_ENABLE_RTTI=ON \
        -DLLVM_BUILD_TESTS=OFF \
        -DLLVM_INSTALL_UTILS=ON \
        -DLLVM_ENABLE_SPHINX=OFF \
        -DLLVM_ENABLE_DOXYGEN=OFF \
        -DLLVM_INSTALL_UTILS=ON \
        -DLLVM_LINK_LLVM_DYLIB=ON \
        -DLLVM_BUILD_LLVM_DYLIB=ON \
        -DCLANG_LINK_CLANG_DYLIB=ON \
        -DSPHINX_WARNINGS_AS_ERRORS=OFF \
        -DLLVM_TARGETS_TO_BUILD=$TARGETS \
        -DCMAKE_SKIP_INSTALL_ALL_DEPENDENCY=ON"

default_cmake_build &&

#This is needed by lld
  pushd ../utils/lit &&
  python3 setup.py install --root=/ -O1 &&
  popd

