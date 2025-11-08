cmake_minimum_required(VERSION 3.10)

project(flucq Fortran)
add_subdirectory(support EXCLUDE_FROM_ALL)

add_executable(flucq
  qdyn.f
  Jstuff.f
  dgesv.f
  ewaldstuff.f
  geniostuff.f
  iostuff.f
  mathstuff.f
  qdynmd.f
  qdynstuff.f
  qpotstuff.f
  ranstuff.f)
set_property(TARGET flucq PROPERTY OUTPUT_NAME_DEBUG dflucq)

add_executable(props
  propsm.f
  Jstuff.f
  dgesv.f
  ewaldstuff.f
  geniostuff.f
  iostuff.f
  mathstuff.f
  qdynmd.f
  qdynstuff.f
  qpotstuff.f
  ranstuff.f)

add_executable(animat
  animain.f
  Jstuff.f
  dgesv.f
  ewaldstuff.f
  geniostuff.f
  iostuff.f
  mathstuff.f
  ranstuff.f
  qdynmd.f
  qdynstuff.f
  qpotstuff.f)

set_target_properties(flucq props animat PROPERTIES Fortran_FORMAT FIXED)
