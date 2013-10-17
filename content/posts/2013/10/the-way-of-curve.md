Title: The way of curve to Haskell
Slug: the-way-of-curve
Date: 2013-10-17 12:00
Author: Vladislav Shikhov
Tags: Haskell

Ubuntu 12.4.x has too old haskell (ghc 7.4.1)

package ghc6 not work (install the same ghc)

install ghc 7.6.3 (
  need libgmp.so.3, sudo apt-get install libgmp3c2
  ./configure 
  make install
  sudo make install
)


compile haskell platform 2013.2 (
  ./configure 
  make install
  sudo make install
)

rm -rf ~/.ghc ~/.cabal (for sure)

/usr/local/bin/cabal update
/usr/local/bin/cabal install cabal-install
cabal update

cabal install c2hs-0.16.4
cabal install cuda-0.5.0.2
cabal install accelarate-cuda

sudo apt-get install llvm

cabal install accelerate-examples

err: error: identifier "__shfl_xor" is undefined

edit /home/hound/.cabal/share/x86_64-linux-ghc-7.6.3/accelerate-cuda-0.13.0.4/cubits/ (
  add #define __CUDA_ARCH__ 100
)

#ifndef __ACCELERATE_CUDA_FUNCTION_H__
#define __ACCELERATE_CUDA_FUNCTION_H__

#define __CUDA_ARCH__ 100

#include <cuda_runtime.h>
#include "accelerate_cuda_type.h"

accelerate-examples --cuda
