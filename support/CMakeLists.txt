cmake_minimum_required(VERSION 3.10)

project(support Fortran)

include_directories(${flucq_SOURCE_DIR})

add_executable(analyz analyz.f ${flucq_SOURCE_DIR}/geniostuff.f)
add_executable(grabcl
  grabcl.f
  ${flucq_SOURCE_DIR}/geniostuff.f
  ${flucq_SOURCE_DIR}/ranstuff.f)

add_executable(hdpe hdpe.f
  ${flucq_SOURCE_DIR}/Jstuff.f
  ${flucq_SOURCE_DIR}/dgesv.f
  ${flucq_SOURCE_DIR}/ewaldstuff.f
  ${flucq_SOURCE_DIR}/geniostuff.f
  ${flucq_SOURCE_DIR}/iostuff.f
  ${flucq_SOURCE_DIR}/mathstuff.f
  ${flucq_SOURCE_DIR}/qdynmd.f
  ${flucq_SOURCE_DIR}/qdynstuff.f
  ${flucq_SOURCE_DIR}/qpotstuff.f
  ${flucq_SOURCE_DIR}/ranstuff.f)

add_executable(stin stin.f ${flucq_SOURCE_DIR}/geniostuff.f)
add_executable(tcorr tcorr.f ${flucq_SOURCE_DIR}/geniostuff.f)

set_target_properties(analyz grabcl hdpe stin tcorr
  PROPERTIES Fortran_FORMAT FIXED)
