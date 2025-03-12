
######################################################################
#  CMakeLists.txt - CMake build file for make to create CBFlib       #
#                                                                    #
#                          Paul Ellis and                            #
#         Herbert J. Bernstein (yaya@bernstein-plus-sons.com)        #
#                                                                    #
# (C) Copyright 2006 - 2018 Herbert J. Bernstein                     #
#                                                                    #
######################################################################

######################################################################
#                                                                    #
# YOU MAY REDISTRIBUTE THE CBFLIB PACKAGE UNDER THE TERMS OF THE GPL #
#                                                                    #
# ALTERNATIVELY YOU MAY REDISTRIBUTE THE CBFLIB API UNDER THE TERMS  #
# OF THE LGPL                                                        #
#                                                                    #
######################################################################

########################### GPL NOTICES ##############################
#                                                                    #
# This program is free software; you can redistribute it and/or      #
# modify it under the terms of the GNU General Public License as     #
# published by the Free Software Foundation; either version 2 of     #
# (the License, or (at your option) any later version.               #
#                                                                    #
# This program is distributed in the hope that it will be useful,    #
# but WITHOUT ANY WARRANTY; without even the implied warranty of     #
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the      #
# GNU General Public License for more details.                       #
#                                                                    #
# You should have received a copy of the GNU General Public License  #
# along with this program; if not, write to the Free Software        #
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA           #
# 02111-1307  USA                                                    #
#                                                                    #
######################################################################

######################### LGPL NOTICES ###############################
#                                                                    #
# This library is free software; you can redistribute it and/or      #
# modify it under the terms of the GNU Lesser General Public         #
# License as published by the Free Software Foundation; either       #
# version 2.1 of the License, or (at your option) any later version. #
#                                                                    #
# This library is distributed in the hope that it will be useful,    #
# but WITHOUT ANY WARRANTY; without even the implied warranty of     #
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU  #
# Lesser General Public License for more details.                    #
#                                                                    #
# You should have received a copy of the GNU Lesser General Public   #
# License along with this library; if not, write to the Free         #
# Software Foundation, Inc., 51 Franklin St, Fifth Floor, Boston,    #
# MA  02110-1301  USA                                                #
#                                                                    #
######################################################################

######################################################################
#                                                                    #
#                    Stanford University Notices                     #
#  for the CBFlib software package that incorporates SLAC software   #
#                 on which copyright is disclaimed                   #
#                                                                    #
# This software                                                      #
# -------------                                                      #
# The term "this software", as used in these Notices, refers to      #
# those portions of the software package CBFlib that were created by #
# employees of the Stanford Linear Accelerator Center, Stanford      #
# University.                                                        #
#                                                                    #
# Stanford disclaimer of copyright                                   #
# --------------------------------                                   #
# Stanford University, owner of the copyright, hereby disclaims its  #
# copyright and all other rights in this software.  Hence, anyone    #
# may freely use it for any purpose without restriction.             #
#                                                                    #
# Acknowledgement of sponsorship                                     #
# ------------------------------                                     #
# This software was produced by the Stanford Linear Accelerator      #
# Center, Stanford University, under Contract DE-AC03-76SFO0515 with #
# the Department of Energy.                                          #
#                                                                    #
# Government disclaimer of liability                                 #
# ----------------------------------                                 #
# Neither the United States nor the United States Department of      #
# Energy, nor any of their employees, makes any warranty, express or #
# implied, or assumes any legal liability or responsibility for the  #
# accuracy, completeness, or usefulness of any data, apparatus,      #
# product, or process disclosed, or represents that its use would    #
# not infringe privately owned rights.                               #
#                                                                    #
# Stanford disclaimer of liability                                   #
# --------------------------------                                   #
# Stanford University makes no representations or warranties,        #
# express or implied, nor assumes any liability for the use of this  #
# software.                                                          #
#                                                                    #
# Maintenance of notices                                             #
# ----------------------                                             #
# In the interest of clarity regarding the origin and status of this #
# software, this and all the preceding Stanford University notices   #
# are to remain affixed to any copy or derivative of this software   #
# made or distributed by the recipient and are to be affixed to any  #
# copy of software made or distributed by the recipient that         #
# contains a copy or derivative of this software.                    #
#                                                                    #
# Based on SLAC Software Notices, Set 4                              #
# OTT.002a, 2004 FEB 03                                              #
######################################################################



######################################################################
#                               NOTICE                               #
# Creative endeavors depend on the lively exchange of ideas. There   #
# are laws and customs which establish rights and responsibilities   #
# for authors and the users of what authors create.  This notice     #
# is not intended to prevent you from using the software and         #
# documents in this package, but to ensure that there are no         #
# misunderstandings about terms and conditions of such use.          #
#                                                                    #
# Please read the following notice carefully.  If you do not         #
# understand any portion of this notice, please seek appropriate     #
# professional legal advice before making use of the software and    #
# documents included in this software package.  In addition to       #
# whatever other steps you may be obliged to take to respect the     #
# intellectual property rights of the various parties involved, if   #
# you do make use of the software and documents in this package,     #
# please give credit where credit is due by citing this package,     #
# its authors and the URL or other source from which you obtained    #
# it, or equivalent primary references in the literature with the    #
# same authors.                                                      #
#                                                                    #
# Some of the software and documents included within this software   #
# package are the intellectual property of various parties, and      #
# placement in this package does not in any way imply that any       #
# such rights have in any way been waived or diminished.             #
#                                                                    #
# With respect to any software or documents for which a copyright    #
# exists, ALL RIGHTS ARE RESERVED TO THE OWNERS OF SUCH COPYRIGHT.   #
#                                                                    #
# Even though the authors of the various documents and software      #
# found here have made a good faith effort to ensure that the        #
# documents are correct and that the software performs according     #
# to its documentation, and we would greatly appreciate hearing of   #
# any problems you may encounter, the programs and documents any     #
# files created by the programs are provided **AS IS** without any   *
# warranty as to correctness, merchantability or fitness for any     #
# particular or general use.                                         #
#                                                                    #
# THE RESPONSIBILITY FOR ANY ADVERSE CONSEQUENCES FROM THE USE OF    #
# PROGRAMS OR DOCUMENTS OR ANY FILE OR FILES CREATED BY USE OF THE   #
# PROGRAMS OR DOCUMENTS LIES SOLELY WITH THE USERS OF THE PROGRAMS   #
# OR DOCUMENTS OR FILE OR FILES AND NOT WITH AUTHORS OF THE          #
# PROGRAMS OR DOCUMENTS.                                             #
######################################################################

######################################################################
#                                                                    #
#                           The IUCr Policy                          #
#      for the Protection and the Promotion of the STAR File and     #
#     CIF Standards for Exchanging and Archiving Electronic Data     #
#                                                                    #
# Overview                                                           #
#                                                                    #
# The Crystallographic Information File (CIF)[1] is a standard for   #
# information interchange promulgated by the International Union of  #
# Crystallography (IUCr). CIF (Hall, Allen & Brown, 1991) is the     #
# recommended method for submitting publications to Acta             #
# Crystallographica Section C and reports of crystal structure       #
# determinations to other sections of Acta Crystallographica         #
# and many other journals. The syntax of a CIF is a subset of the    #
# more general STAR File[2] format. The CIF and STAR File approaches #
# are used increasingly in the structural sciences for data exchange #
# and archiving, and are having a significant influence on these     #
# activities in other fields.                                        #
#                                                                    #
# Statement of intent                                                #
#                                                                    #
# The IUCr's interest in the STAR File is as a general data          #
# interchange standard for science, and its interest in the CIF,     #
# a conformant derivative of the STAR File, is as a concise data     #
# exchange and archival standard for crystallography and structural  #
# science.                                                           #
#                                                                    #
# Protection of the standards                                        #
#                                                                    #
# To protect the STAR File and the CIF as standards for              #
# interchanging and archiving electronic data, the IUCr, on behalf   #
# of the scientific community,                                       #
#                                                                    #
# # holds the copyrights on the standards themselves,                *
#                                                                    #
# # owns the associated trademarks and service marks, and            *
#                                                                    #
# # holds a patent on the STAR File.                                 *
#                                                                    #
# These intellectual property rights relate solely to the            #
# interchange formats, not to the data contained therein, nor to     #
# the software used in the generation, access or manipulation of     #
# the data.                                                          #
#                                                                    #
# Promotion of the standards                                         #
#                                                                    #
# The sole requirement that the IUCr, in its protective role,        #
# imposes on software purporting to process STAR File or CIF data    #
# is that the following conditions be met prior to sale or           #
# distribution.                                                      #
#                                                                    #
# # Software claiming to read files written to either the STAR       *
# File or the CIF standard must be able to extract the pertinent     #
# data from a file conformant to the STAR File syntax, or the CIF    #
# syntax, respectively.                                              #
#                                                                    #
# # Software claiming to write files in either the STAR File, or     *
# the CIF, standard must produce files that are conformant to the    #
# STAR File syntax, or the CIF syntax, respectively.                 #
#                                                                    #
# # Software claiming to read definitions from a specific data       *
# dictionary approved by the IUCr must be able to extract any        #
# pertinent definition which is conformant to the dictionary         #
# definition language (DDL)[3] associated with that dictionary.      #
#                                                                    #
# The IUCr, through its Committee on CIF Standards, will assist      #
# any developer to verify that software meets these conformance      #
# conditions.                                                        #
#                                                                    #
# Glossary of terms                                                  #
#                                                                    #
# [1] CIF:  is a data file conformant to the file syntax defined     #
# at http://www.iucr.org/iucr-top/cif/spec/index.html                #
#                                                                    #
# [2] STAR File:  is a data file conformant to the file syntax       #
# defined at http://www.iucr.org/iucr-top/cif/spec/star/index.html   #
#                                                                    #
# [3] DDL:  is a language used in a data dictionary to define data   #
# items in terms of "attributes". Dictionaries currently approved    #
# by the IUCr, and the DDL versions used to construct these          #
# dictionaries, are listed at                                        #
# http://www.iucr.org/iucr-top/cif/spec/ddl/index.html               #
#                                                                    #
# Last modified: 30 September 2000                                   #
#                                                                    #
# IUCr Policy Copyright (C) 2000 International Union of              #
# Crystallography                                                    #
######################################################################

######################################################################
#  CMakeLists.txt for CBFlib                                         #
#                                                                    #
#  Assumed directory structure                                       #
#    CMAKE_CURRENT_SOURCE_DIR CBFlib kit containing this file        #
#      doc                    Directory with documentation           #
#      examples               Directory with example programs        #
#      include                Directory with header files            #
#      m4                     Directory with m4 files                #
#      src                    Directory with source files            #
#                                                                    #
#    CMAKE_CURRENT_BINARY_DIR CBFlib build directory                 #
#      bin                    Directory for executable programs      #
#      include                Directory with build-created headers   #
#      src                    Directory with build-created source    #
#      lib                    Libraries, shared and static           #
#      jcbf                   Java module                            #
#      pycbf                  Python module                          #
#                                                                    #
# External dependencies in ${CMAKE_CURRENT_BINARY_DIR}:              #
#    _deps                    Directory for HDF5, LibTIFF, etc.      #
#      data_input-*           Input test data                        #
#      data_output-*          Reference output test data             #
#    cqrlib-prefix            cqrlib-1.1.4                           #
#    hdf5-prefix              hdf5-1.14.4.2                          #
#    libtiff-prefix           libtiff-4.0.9                          #
#    pcre-prefix              pcre-8.38 (where needed)               #
#                                                                    #
######################################################################

# ${CMAKE_COMMAND} -E rm was introduced in CMake 3.17, which also
# deprecated ${CMAKE_COMMAND} -E remove.
cmake_minimum_required(VERSION 3.17)
project(CBFlib
  LANGUAGES C CXX
  VERSION 0.9.7)
set(VERSION_INFO "3:0:1")


# Set timestamps of extracted contents to the time of extraction.
# Resolved by explicitly setting DOWNLOAD_EXTRACT_TIMESTAMP in
# externalproject_add() or fetchcontent_declare(), but the option was
# only introduced in CMake 3.24.
cmake_policy(SET CMP0135 NEW)


# Output directories for static and shared libraries as well as
# binaries.  These appear to be required to on Windows and for running
# h5dump elsewhere.
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/lib")
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/lib")
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "${PROJECT_BINARY_DIR}/bin")

option(BUILD_SHARED_LIBS "Build using shared libraries" ON)

option(CBF_ENABLE_FORTRAN "Enable FORTRAN90" ON)
if(CBF_ENABLE_FORTRAN)
  include(CheckLanguage)
  check_language(Fortran)
  if(CMAKE_Fortran_COMPILER)
    enable_language(Fortran)
  else()
    message(FATAL_ERROR "FORTRAN90 support requested, but no compiler found")
  endif()
endif()

option(CBF_ENABLE_ULP "Enable ULP" OFF)


#
# Java and Python bindings
#
# The modules can only be built when BUILD_SHARED_LIBS is set.  Java
# should only require openjdk-17-jdk-headless (on Debian) but AWT
# requires openjdk-17-jdk?
if(BUILD_SHARED_LIBS)
  option(CBF_ENABLE_JAVA "Enable Java" ON)
  option(CBF_ENABLE_PYTHON "Enable Python" ON)
endif()


# Check for missing functions: fgetln(3) is in 4.4BSD; realpath(3) is
# in 4.4BSD, POSIX.1-2001; regcomp(3) is in POSIX.1-2001,
# POSIX.1-2008.
include(CheckIncludeFile)
check_include_file("unistd.h" HAVE_UNISTD_H)
if(HAVE_UNISTD_H)
  add_compile_definitions("HAVE_UNISTD_H")
endif()

include(CheckSymbolExists)
check_symbol_exists(fgetln "stdio.h" HAVE_FGETLN)
if(HAVE_FGETLN)
  add_compile_definitions("HAVE_FGETLN")
endif()

check_symbol_exists(mkstemp "stdlib.h" HAVE_MKSTEMP)
if(HAVE_MKSTEMP)
  add_compile_definitions("HAVE_MKSTEMP")
endif()

check_symbol_exists(realpath "stdlib.h" HAVE_REALPATH)
if(HAVE_REALPATH)
  add_compile_definitions("HAVE_REALPATH")
endif()

check_symbol_exists(regcomp "regex.h" HAVE_REGCOMP)


#
# Directories on the kit side
set(EXAMPLES  "${CMAKE_CURRENT_SOURCE_DIR}/examples")
set(INCLUDE   "${CMAKE_CURRENT_SOURCE_DIR}/include")
set(SRC       "${CMAKE_CURRENT_SOURCE_DIR}/src")
set(TEMPLATES "${CMAKE_CURRENT_SOURCE_DIR}/templates")


# Under the (Linux) libtool convention, the single-component SOVERSION
# is the difference between the current and age components of
# VERSION_INFO.
string(REPLACE ":" ";" _cra "${VERSION_INFO}")
list(GET _cra 0 _current)
list(GET _cra 2 _age)
math(EXPR SOVERSION "${_current} - ${_age}")


#
# Definitions to get dependencies.
#
# The --binary option appears to be required for patching the test
# data on MSYS2.
find_program(PATCH patch)
include(FetchContent)

fetchcontent_declare(data_input
  URL "http://downloads.sf.net/cbflib/CBFlib_${PROJECT_VERSION}_Data_Files_Input.tar.gz"
  URL_HASH MD5=a49ea3efad110189eb3049ab942006ce # 0.9.7
  #URL_HASH f98ae4214b3e57acb42437ea4b685c4d # 0.9.8
  PATCH_COMMAND "${PATCH}"
    -Np1 -i "${CMAKE_CURRENT_SOURCE_DIR}/patches/cbflib-data-input-${PROJECT_VERSION}.patch" -t --binary)

fetchcontent_declare(data_output
  URL "http://downloads.sf.net/cbflib/CBFlib_${PROJECT_VERSION}_Data_Files_Output.tar.gz"
  URL_HASH MD5=53e1a5fef1b97a9913e963aa41b7c374 # 0.9.7
  #URL_HASH MD5=edde13b20baf16bb9ab91cfc647ba4d6 # 0.9.8
  PATCH_COMMAND "${PATCH}"
    -Np1 -i "${CMAKE_CURRENT_SOURCE_DIR}/patches/cbflib-data-output-${PROJECT_VERSION}.patch" -t --binary)


#
# libm
set(libm "$<$<NOT:$<C_COMPILER_ID:MSVC>>:m>")


#
# General remarks about external projects:
#
#   * If a cloned repository is patched, CMake seems to attempt to
#     invoke PATCH_COMMAND on every run.  For now, avoid automatically
#     patching cloned repositories.
#
#   * Cannot set INTERFACE_INCLUDE_DIRECTORIES on an imported target
#     to a non-existent path: for now, create a directory now that
#     will be populated during build.
#
#   * External projects must generally be installed somewhere for
#     examples to run in-tree on Windows.  Here external projects are
#     installed to CMAKE_RUNTIME_OUTPUT_DIRECTORY and
#     CMAKE_LIBRARY_OUTPUT_DIRECTORY rather than CMAKE_INSTALL_PREFIX,
#     and their targets are not exported.
#
#   * Do not bother running any tests.

# Appends the full path to LIBRARIES to OUTPUT.  DLL platforms are AIX
# and Windows (https://gitlab.kitware.com/cmake/cmake/-/issues/25681).
function(append_library_directory)
  cmake_parse_arguments(PARSE_ARGV 0 APPEND_LIBRARY_DIRECTORY
    ""
    "OUTPUT"
    "LIBRARIES")

  if(BUILD_SHARED_LIBS)
    if(CMAKE_SYSTEM_NAME STREQUAL "AIX"
        OR CMAKE_SYSTEM_NAME STREQUAL "Windows")
      set(_dir "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}")
    else()
      set(_dir "${CMAKE_LIBRARY_OUTPUT_DIRECTORY}")
    endif()
    set(_pre "${CMAKE_SHARED_LIBRARY_PREFIX}")
    set(_suf "${CMAKE_SHARED_LIBRARY_SUFFIX}")
  else()
    set(_dir "${CMAKE_LIBRARY_OUTPUT_DIRECTORY}")
    set(_pre "${CMAKE_STATIC_LIBRARY_PREFIX}")
    set(_suf "${CMAKE_STATIC_LIBRARY_SUFFIX}")
  endif()

  set(_lst "")
  foreach(_lib IN LISTS APPEND_LIBRARY_DIRECTORY_LIBRARIES)
    list(APPEND _lst "${_dir}/${_pre}${_lib}${_suf}")
  endforeach()
  set(${APPEND_LIBRARY_DIRECTORY_OUTPUT} ${_lst} PARENT_SCOPE)
endfunction()


#
# CQRlib
#
# Not required for 0.9.7; cif2cbf depends on CQRlib starting with
# 0.9.8.
# set(CBF_WITH_CQRLIB ON CACHE BOOL
#   "Link against internally built CQRlib library")
# mark_as_advanced(CBF_WITH_CQRLIB)

# if(CBF_WITH_CQRLIB)
#   append_library_directory(LIBRARIES "CQRlib" OUTPUT _cqrlib)
#   include(ExternalProject)
#   externalproject_add(cqrlib
#     URL https://github.com/yayahjb/cqrlib/archive/refs/tags/CQRlib-1.1.4.tar.gz
#     PATCH_COMMAND "${PATCH}"
#       -N -i "${CMAKE_CURRENT_SOURCE_DIR}/patches/cqrlib-1.1.4.patch" -p 1 -t
#     BUILD_BYPRODUCTS "${_cqrlib}"
#     CMAKE_CACHE_ARGS
#       "-DCMAKE_BUILD_TYPE:STRING=${CMAKE_BUILD_TYPE}"
#       "-DCMAKE_INSTALL_BINDIR:PATH=${CMAKE_RUNTIME_OUTPUT_DIRECTORY}"
#       "-DCMAKE_INSTALL_INCLUDEDIR:PATH=${CMAKE_CURRENT_BINARY_DIR}/include/cqrlib"
#       "-DCMAKE_INSTALL_LIBDIR:PATH=${CMAKE_LIBRARY_OUTPUT_DIRECTORY}"
#       "-DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_CURRENT_BINARY_DIR}")

#   file(MAKE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/include/cqrlib")
#   if(BUILD_SHARED_LIBS)
#     add_library(CQR SHARED IMPORTED)
#     set_target_properties(CQR PROPERTIES
#       IMPORTED_IMPLIB "${_cqrlib}")
#   else()
#     add_library(CQR STATIC IMPORTED)
#   endif()
#   add_dependencies(CQR cqrlib)
#   set_target_properties(CQR PROPERTIES
#     INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_BINARY_DIR}/include/cqrlib"
#     IMPORTED_LOCATION "${_cqrlib}")

# else()
#   set(CQRLIB_INCLUDE_DIR "" CACHE FILEPATH
#     "CQRlib include directory")
#   mark_as_advanced(CQRLIB_INCLUDE_DIR)

#   set(CQRLIB_LIBRARY "" CACHE FILEPATH
#     "CQRlib library")
#   mark_as_advanced(CQRLIB_LIBRARY)

#   if(BUILD_SHARED_LIBS)
#     add_library(CQR SHARED IMPORTED)
#     set_target_properties(CQR PROPERTIES
#       IMPORTED_IMPLIB "${CQRLIB_LIBRARY}")
#   else()
#     add_library(CQR SHARED IMPORTED)
#   endif()
#   set_target_properties(CQR PROPERTIES
#     IMPORTED_IMPLIB "${CQRLIB_LIBRARY}"
#     INTERFACE_INCLUDE_DIRECTORIES "${CQRLIB_INCLUDE_DIR}")

#   # Alternatively, find CQRlib using its CMake Config-file.  This will
#   # not work in the general case until CQRlib has CMake support.
#   #find_package(CQRlib CONFIG REQUIRED)
#   #add_library(CQR ALIAS CQR::CQR)
# endif()


#
# HDF5
#
# See hdf5's root CMakeLists.txt and config/cmake/HDFLibMacros.cmake.
#
# Here: must set _h5dump_executable to the path to h5dump and
# _hdf5_target to the real (unaliased) HDF5 target.  Note that HDF5 is
# a PUBLIC dependency of CBFlib, because cbf_hdf5.h includes hdf5.h.
set(CBF_WITH_HDF5 ON CACHE BOOL
  "Link against internally built HDF5 library")
mark_as_advanced(CBF_WITH_HDF5)

set(HDF5REGISTER "--register" "manual" CACHE INTERNAL
  "Flags to register HDF5 plugins")
mark_as_advanced(HDF5REGISTER)

if(CBF_WITH_HDF5)
  # It seems CMAKE_INSTALL_LIBDIR (and similarly,
  # HDF5_INSTALL_BIN_DIR, HDF5_INSTALL_INCLUDE_DIR, and
  # HDF5_INSTALL_LIB_DIR) need to be relative to CMAKE_INSTALL_PREFIX,
  # otherwise the HDF5 buildsystem wrecks RPATH (it appears to always
  # be relative to $ORIGIN).
  #
  # HDF5_GENERATE_HEADERS triggers rebuild on every change to the
  # parent CMakeLists.txt if set; see
  # https://forum.hdfgroup.org/t/issues-when-using-hdf5-as-a-git-submodule-and-using-cmake-with-add-subdirectory/7189/2.
  # This does not matter when building with externalproject_add().
  append_library_directory(LIBRARIES "hdf5" OUTPUT _libhdf5)
  include(ExternalProject)
  externalproject_add(hdf5
    GIT_REPOSITORY https://github.com/HDFGroup/hdf5.git
    GIT_TAG f0ecc8bc26972119fb31b1cd548ea23fff4a3227 # hdf5_1.14.4.2
    BUILD_BYPRODUCTS "${_libhdf5}"
    CMAKE_CACHE_ARGS
      "-DBUILD_TESTING:BOOL=OFF"
      "-DCMAKE_BUILD_TYPE:STRING=${CMAKE_BUILD_TYPE}"
      "-DCMAKE_INSTALL_BINDIR:PATH=bin"
      "-DCMAKE_INSTALL_DATAROOTDIR:PATH=share/hdf5"
      "-DCMAKE_INSTALL_INCLUDEDIR:PATH=include/hdf5"
      "-DCMAKE_INSTALL_LIBDIR:PATH=lib"
      "-DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_CURRENT_BINARY_DIR}"
      "-DHDF5_BUILD_CPP_LIB:BOOL=OFF"
      "-DHDF5_BUILD_TOOLS:BOOL=ON"
      "-DHDF5_ENABLE_FORTRAN:BOOL=$<IF:$<BOOL:${CBF_ENABLE_FORTRAN}>,ON,OFF>"
      #"-DHDF5_GENERATE_HEADERS:BOOL=OFF"
      "-DHDF5_USE_GNU_DIRS:BOOL=TRUE")

  set(_h5dump_executable
    "${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/h5dump${CMAKE_EXECUTABLE_SUFFIX}")

  file(MAKE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/include/hdf5")
  if(BUILD_SHARED_LIBS)
    add_library(HDF5 SHARED IMPORTED)
    set_target_properties(HDF5 PROPERTIES
      IMPORTED_IMPLIB "${_libhdf5}")
  else()
    add_library(HDF5 STATIC IMPORTED)
  endif()
  add_dependencies(HDF5 hdf5)
  set_target_properties(HDF5 PROPERTIES
    INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_BINARY_DIR}/include/hdf5"
    IMPORTED_LOCATION "${_libhdf5}")
  set(_hdf5_target HDF5)

else()
  if(NOT BUILD_SHARED_LIBS)
    set(HDF5_USE_STATIC_LIBRARIES TRUE)
  endif()
  find_package(HDF5 REQUIRED)
  find_program(_h5dump_executable h5dump)

  if(TARGET hdf5::hdf5)
    # The hdf5::hdf5 target for the C library was introduced in CMake
    # 3.19.  Internally, HDF5 has hdf5-shared and hdf5-static targets,
    # but those may not be exported.
    add_library(HDF5 ALIAS hdf5::hdf5)
    set(_hdf5_target hdf5::hdf5)
  else()
    if(BUILD_SHARED_LIBS)
      add_library(HDF5 SHARED IMPORTED)
      set_target_properties(HDF5 PROPERTIES
        IMPORTED_IMPLIB "${HDF5_C_LIBRARIES}")
    else()
      add_library(HDF5 STATIC IMPORTED)
    endif()
    set_target_properties(HDF5 PROPERTIES
      IMPORTED_LOCATION "${HDF5_C_LIBRARIES}"
      INTERFACE_INCLUDE_DIRECTORIES "${HDF5_C_INCLUDE_DIRS}")
    set(_hdf5_target HDF5)
  endif()
endif()


if(NOT TARGET h5dump)
  add_executable(h5dump IMPORTED)
  set_target_properties(h5dump PROPERTIES
    IMPORTED_LOCATION "${_h5dump_executable}")
endif()


# CBFlib must be compiled with H5_USE_110_API.  With MSVC, also need
# H5_BUILT_AS_DYNAMIC_LIB if HDF5 is a dynamic library.
target_compile_definitions(${_hdf5_target}
  INTERFACE H5_USE_110_API)
if(BUILD_SHARED_LIBS)
  target_compile_definitions(${_hdf5_target}
    INTERFACE H5_BUILT_AS_DYNAMIC_LIB)
endif()


#
# PCRE
#
# Linking against an external PCRE1 library (no longer maintained)
# with a libc that has the regex functions will define regcomp,
# regerror, regexec, and regfree twice: do not set CBF_WITH_PCRE if
# libc has the regexec functions.  PCRE2 does it differently: it
# defines the regex functions prefixed by pcre2_ and maps them onto
# the unprefixed names with preprocessor directives.
set(CBF_WITH_PCRE ON CACHE BOOL
  "Link against internally built Perl-compatible expressions library")
mark_as_advanced(CBF_WITH_PCRE)

if(HAVE_REGCOMP)
  add_library(pcreposix INTERFACE IMPORTED)
  target_compile_definitions(pcreposix
    INTERFACE CBF_REGEXLIB_REGEX)

elseif(CBF_WITH_PCRE)
  # Do not try to link PCRE with readline, because its build system
  # does not catch the libtinfo dependency (for tputs and friends).
  # Note that PCRE-8.38 is not using GNUInstallDirs; later version
  # may.
  append_library_directory(LIBRARIES "pcreposix" OUTPUT _pcreposix) # Also pcre?
  include(ExternalProject)
  externalproject_add(pcre
    URL "http://downloads.sf.net/cbflib/pcre-8.38.tar.gz"
    #GIT_REPOSITORY https://github.com/PCRE2Project/pcre2
    #GIT_TAG 3864abdb713f78831dd12d898ab31bbb0fa630b6 # PCRE2-10.43
    BUILD_BYPRODUCTS "${_pcreposix}"
    CMAKE_CACHE_ARGS
      "-DBUILD_SHARED_LIBS:BOOL=${BUILD_SHARED_LIBS}"
      "-DCMAKE_BUILD_TYPE:STRING=${CMAKE_BUILD_TYPE}"
      "-DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_CURRENT_BINARY_DIR}"
      "-DPCRE_BUILD_TESTS:BOOL=OFF"
      "-DPCRE_SUPPORT_LIBEDIT:BOOL=OFF"
      "-DPCRE_SUPPORT_LIBREADLINE:BOOL=OFF")

  file(MAKE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/include")
  if(BUILD_SHARED_LIBS)
    add_library(pcreposix SHARED IMPORTED)
    set_target_properties(pcreposix PROPERTIES
      IMPORTED_IMPLIB "${_pcreposix}")
  else()
    add_library(pcreposix STATIC IMPORTED)
  endif()
  add_dependencies(pcreposix pcre)
  set_target_properties(pcreposix PROPERTIES
    INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_BINARY_DIR}/include"
    IMPORTED_LOCATION "${_pcreposix}")

else()
  set(PCRE_INCLUDE_DIR "" CACHE FILEPATH
    "Perl-compatible regular expressions include directory")
  mark_as_advanced(PCRE_INCLUDE_DIR)

  set(PCRE_LIBRARY "" CACHE FILEPATH
    "Perl-compatible regular expressions library")
  mark_as_advanced(PCRE_LIBRARY)

  add_library(pcreposix UNKNOWN IMPORTED)
  set_target_properties(pcreposix PROPERTIES
    IMPORTED_LOCATION "${PCRE_LIBRARY}"
    INTERFACE_INCLUDE_DIRECTORIES "${PCRE_INCLUDE_DIR}")
endif()


#
# TIFF
#
# LibTIFF to support tiff2cbf.  Disable tests if building in-tree; the
# tiff-tests cache variable was introduced in LibTIFF 4.5.0.
set(CBF_WITH_LIBTIFF ON CACHE BOOL
  "Link against internally built LibTIFF library")
mark_as_advanced(CBF_WITH_LIBTIFF)

if(CBF_WITH_LIBTIFF)
  # The first LibTIFF at https://gitlab.com/libtiff/libtiff with
  # native CMake support seems to be 4.0.5.  The first version that
  # builds on current MSYS2 is 4.0.9.
  #
  # 4.0.3-rev-29Sep13 appears to have CMakeLists.txt patched in but
  # fails on MSYS2: multiple definition of ua_wcsicmp.
  append_library_directory(LIBRARIES "tiff" OUTPUT _libtiff)
  include(ExternalProject)
  externalproject_add(libtiff
    #URL http://downloads.sf.net/cbflib/tiff-4.0.3-rev-29Sep13.tar.gz
    GIT_REPOSITORY https://gitlab.com/libtiff/libtiff
    GIT_TAG 020bd2fd3b4235b2175dafa9633d2b191c50e7cd # 4.0.9
    BUILD_BYPRODUCTS "${_libtiff}"
    CMAKE_CACHE_ARGS
      "-DCMAKE_BUILD_TYPE:STRING=${CMAKE_BUILD_TYPE}"
      "-DCMAKE_INSTALL_BINDIR:PATH=${CMAKE_RUNTIME_OUTPUT_DIRECTORY}"
      "-DCMAKE_INSTALL_DATAROOTDIR:PATH=${CMAKE_CURRENT_BINARY_DIR}/share/libtiff"
      "-DCMAKE_INSTALL_INCLUDEDIR:PATH=${CMAKE_CURRENT_BINARY_DIR}/include/libtiff"
      "-DCMAKE_INSTALL_LIBDIR:PATH=${CMAKE_LIBRARY_OUTPUT_DIRECTORY}"
      "-DCMAKE_INSTALL_PREFIX:PATH=${CMAKE_CURRENT_BINARY_DIR}"
      "-Dtiff-contrib:BOOL=OFF"
      "-Dtiff-docs:BOOL=OFF"
      "-Dtiff-tests:BOOL=OFF"
      "-Dtiff-tools:BOOL=OFF")

  file(MAKE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/include/libtiff")
  if(BUILD_SHARED_LIBS)
    add_library(tiff SHARED IMPORTED)
    set_target_properties(tiff PROPERTIES
      IMPORTED_IMPLIB "${_libtiff}")
  else()
    add_library(tiff STATIC IMPORTED)
  endif()
  add_dependencies(tiff libtiff)
  set_target_properties(tiff PROPERTIES
    INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_BINARY_DIR}/include/libtiff"
    IMPORTED_LOCATION "${_libtiff}")

else()
  find_package(TIFF REQUIRED)
  add_library(tiff ALIAS TIFF::TIFF)
endif()


#
# INPUT/OUTPUT TEST DATA
#
# If CBF_DATA_INPUT and/or CBF_DATA_OUTPUT are set externally, the
# test data in the corresponding directories are assumed to be
# patched.
set(CBF_DATA_INPUT "" CACHE FILEPATH
  "Path to input test data directory")
mark_as_advanced(CBF_DATA_INPUT)

if(NOT CBF_DATA_INPUT)
  fetchcontent_makeavailable(data_input)
  set(CBF_DATA_INPUT "${data_input_SOURCE_DIR}/CBFlib_0.9.7_Data_Files_Input")
endif()

set(CBF_DATA_OUTPUT "" CACHE FILEPATH
  "Path to reference output test data directory")
mark_as_advanced(CBF_DATA_OUTPUT)

if(NOT CBF_DATA_OUTPUT)
  fetchcontent_makeavailable(data_output)
  set(CBF_DATA_OUTPUT "${data_output_SOURCE_DIR}")
endif()


#
# CBF (with headers), builds and installs a shared libcbf unless
# configured with BUILD_SHARED_LIBS=OFF.
add_library(CBF
  "${SRC}/cbf.c"
  "${SRC}/cbf_airy_disk.c"
  "${SRC}/cbf_alloc.c"
  #"${SRC}/cbf_array2minicbf.c" # not in 0.9.7
  "${SRC}/cbf_ascii.c"
  "${SRC}/cbf_binary.c"
  "${SRC}/cbf_byte_offset.c"
  "${SRC}/cbf_canonical.c"
  "${SRC}/cbf_codes.c"
  "${SRC}/cbf_compress.c"
  "${SRC}/cbf_context.c"
  "${SRC}/cbf_copy.c"
  "${SRC}/cbf_file.c"
  "${SRC}/cbf_getopt.c"
  "${SRC}/cbf_hdf5.c"
  "${SRC}/cbf_hdf5_filter.c"
  "${SRC}/cbf_lex.c"
  "${SRC}/cbf_minicbf_header.c"
  "${SRC}/cbf_nibble_offset.c"
  "${SRC}/cbf_packed.c"
  "${SRC}/cbf_predictor.c"
  "${SRC}/cbf_read_binary.c"
  "${SRC}/cbf_read_mime.c"
  "${SRC}/cbf_simple.c"
  "${SRC}/cbf_string.c"
  "${SRC}/cbf_stx.c"
  "${SRC}/cbf_tree.c"
  "${SRC}/cbf_uncompressed.c"
  "${SRC}/cbf_write.c"
  "${SRC}/cbf_write_binary.c"
  "${SRC}/cbf_ws.c"
  "${SRC}/cbff.c"
  "${SRC}/md5c.c"
  "${SRC}/img.c")
if(CBF_ENABLE_ULP)
  target_compile_definitions(CBF PUBLIC CBF_USE_ULP)
  target_sources(CBF PRIVATE "${SRC}/cbf_ulp.c")
endif()
if(NOT HAVE_REALPATH)
  target_sources(CBF PRIVATE "${SRC}/realpath.c")
endif()

set(headers
  "${INCLUDE}/cbf.h"
  "${INCLUDE}/cbf_airy_disk.h"
  "${INCLUDE}/cbf_alloc.h"
  #"${INCLUDE}/cbf_array2minicbf.h" # not in 0.9.7
  "${INCLUDE}/cbf_ascii.h"
  "${INCLUDE}/cbf_binary.h"
  "${INCLUDE}/cbf_byte_offset.h"
  "${INCLUDE}/cbf_canonical.h"
  "${INCLUDE}/cbf_codes.h"
  "${INCLUDE}/cbf_compress.h"
  "${INCLUDE}/cbf_context.h"
  "${INCLUDE}/cbf_copy.h"
  "${INCLUDE}/cbf_file.h"
  "${INCLUDE}/cbf_getopt.h"
  "${INCLUDE}/cbf_hdf5.h"
  "${INCLUDE}/cbf_hdf5_filter.h"
  "${INCLUDE}/cbf_lex.h"
  "${INCLUDE}/cbf_minicbf_header.h"
  "${INCLUDE}/cbf_nibble_offset.h"
  "${INCLUDE}/cbf_packed.h"
  "${INCLUDE}/cbf_predictor.h"
  "${INCLUDE}/cbf_read_binary.h"
  "${INCLUDE}/cbf_read_mime.h"
  "${INCLUDE}/cbf_simple.h"
  "${INCLUDE}/cbf_string.h"
  "${INCLUDE}/cbf_stx.h"
  "${INCLUDE}/cbf_tree.h"
  "${INCLUDE}/cbf_uncompressed.h"
  "${INCLUDE}/cbf_write.h"
  "${INCLUDE}/cbf_write_binary.h"
  "${INCLUDE}/cbf_ws.h"
  "${INCLUDE}/global.h"
  "${INCLUDE}/cbff.h"
  "${INCLUDE}/md5.h"
  "${INCLUDE}/img.h")
if(CBF_ENABLE_ULP)
  list(APPEND headers
    "${INCLUDE}/cbf_ulp.h")
endif()

set_target_properties(CBF PROPERTIES
  OUTPUT_NAME "cbf"
  PUBLIC_HEADER "${headers}"
  SOVERSION "${SOVERSION}")
target_include_directories(CBF
  PUBLIC "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>"
         "$<INSTALL_INTERFACE:include>")
target_link_libraries(CBF
  PUBLIC HDF5
  PRIVATE pcreposix
  "${libm}")

include(GNUInstallDirs)
install(
  TARGETS
    CBF
  EXPORT CBFlibTargets
  ARCHIVE
    COMPONENT "Development"
  LIBRARY
    COMPONENT "Runtime"
    NAMELINK_COMPONENT "Development"
  PUBLIC_HEADER
    COMPONENT "Development"
    DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}/cbflib"
  RUNTIME
    COMPONENT "Runtime")


#
# CMake configuration files, targets are emitted in the CBF::
# namespace.
export(EXPORT CBFlibTargets
  FILE "${CMAKE_CURRENT_BINARY_DIR}/CBFlibTargets.cmake")
install(
  EXPORT CBFlibTargets
  FILE CBFlibTargets.cmake
  NAMESPACE "CBF::"
  COMPONENT "Development"
  DESTINATION "${CMAKE_INSTALL_LIBDIR}/cmake/${PROJECT_NAME}")

include(CMakePackageConfigHelpers)
configure_package_config_file(${CMAKE_CURRENT_SOURCE_DIR}/Config.cmake.in
  "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake"
  INSTALL_DESTINATION "${CMAKE_INSTALL_LIBDIR}/cmake/${PROJECT_NAME}"
  NO_CHECK_REQUIRED_COMPONENTS_MACRO
  NO_SET_AND_CHECK_MACRO)
write_basic_package_version_file(
  "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}ConfigVersion.cmake"
  COMPATIBILITY SameMajorVersion
  VERSION "${PROJECT_VERSION}")
install(
  FILES "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}Config.cmake"
        "${CMAKE_CURRENT_BINARY_DIR}/${PROJECT_NAME}ConfigVersion.cmake"
  COMPONENT "Development"
  DESTINATION "${CMAKE_INSTALL_LIBDIR}/cmake/${PROJECT_NAME}")


#
# F90SOURCE
#
# Build the FORTRAN sources and libraries.
if(CBF_ENABLE_FORTRAN)
  find_program(M4 m4)
  set(M4FLAGS "-Dfcb_bytes_in_rec=4096" CACHE STRING
    "Flags used by the M4 macro processor during FORTRAN build")
  mark_as_advanced(M4FLAGS)

  file(MAKE_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/src")
  set(CBF_F90_BUILT_SOURCES
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_exit_binary.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_next_binary.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_open_cifin.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_packed.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_read_bits.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_read_image.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_read_xds_i2.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/test_fcb_read_image.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/test_xds_binary.f90")

  foreach(f90src IN LISTS CBF_F90_BUILT_SOURCES)
    get_filename_component(filename "${f90src}" NAME_WE)
    set(f90bldsrc "${CMAKE_CURRENT_BINARY_DIR}/src/${filename}.f90")
    set(f90srcm4 "${CMAKE_CURRENT_SOURCE_DIR}/m4/${filename}.m4")
    add_custom_command(
      OUTPUT "${f90bldsrc}"
      WORKING_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/m4"
      COMMAND ${M4} -P ${M4FLAGS} "${f90srcm4}" > "${f90bldsrc}"
      DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/m4/fcblib_defines.m4"
              "${f90srcm4}"
      COMMENT "Generating ${f90bldsrc}")
  endforeach()

  add_library(FCB
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_exit_binary.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_next_binary.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_open_cifin.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_packed.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_read_bits.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_read_image.f90"
    "${CMAKE_CURRENT_BINARY_DIR}/src/fcb_read_xds_i2.f90"
    "${SRC}/fcb_atol_wcnt.f90"
    "${SRC}/fcb_ci_strncmparr.f90"
    "${SRC}/fcb_nblen_array.f90"
    "${SRC}/fcb_read_byte.f90"
    "${SRC}/fcb_read_line.f90"
    "${SRC}/fcb_skip_whitespace.f90")


  # Stock SWIG-4.0 does not do FORTRAN, so how can CMake's
  # swig_add_library() support FORTRAN since 3.18?
  #swig_add_library(f90cbf
  #  SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/f90cbf/f90cbf.f90"
  #          "${CMAKE_CURRENT_SOURCE_DIR}/f90cbf/f90cbf.i"
  #  LANGUAGE Fortran
  #  OUTPUT_DIR "${CMAKE_CURRENT_BINARY_DIR}/f90cbf")


  # Assume that this is what SWIG would have output.  Apart from an
  # empty line, it appears to be identical to what is output by
  # filtering through convert_f90_swig_wrap.
  add_library(f90cbf
    "${CMAKE_CURRENT_SOURCE_DIR}/f90cbf/f90cbf.f90"
    "${CMAKE_CURRENT_SOURCE_DIR}/f90cbf/f90cbf_wrap.c")
  target_include_directories(f90cbf
    PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/include")
  target_link_libraries(f90cbf
    CBF)
endif()


#
# Java bindings
#
# XXX Where to install this?
if(CBF_ENABLE_JAVA)
  # In recent CMake FindJINI (3.24) and FindSWIG (3.18) support
  # COMPONENTS that could be set to "JVM" and "java" (all lowercase),
  # respectively.
  find_package(Java COMPONENTS Development REQUIRED)
  find_package(JNI REQUIRED)
  find_package(SWIG REQUIRED)
  include(UseJava)
  include(UseSWIG)

  set_property(SOURCE "${SRC}/jcbf.i" PROPERTY
    INCLUDE_DIRECTORIES "${CMAKE_CURRENT_SOURCE_DIR}/include")


  # Generate lib/libcbf_wrap.so as well as ${_java_files_generated}
  # below.
  swig_add_library(cbf_wrap
    SOURCES "${SRC}/jcbf.i"
    LANGUAGE Java
    OUTPUT_DIR "${CMAKE_CURRENT_BINARY_DIR}/jcbf")
  set_property(TARGET cbf_wrap PROPERTY
    SWIG_COMPILE_OPTIONS -package org.iucr.cbflib)
  target_include_directories(cbf_wrap
    PRIVATE "${JAVA_INCLUDE_PATH}"
            "${JAVA_INCLUDE_PATH2}")
  target_link_libraries(cbf_wrap
    CBF)


  # Enumerate the generated files.  Cannot use file(GLOB ...) here,
  # because that is executed at configuration time, at which point
  # "jcbf" may not exist.  get_property(... SWIG_SUPPORT_FILES) only
  # returns "jcbf/cbf.java" and "jcbf/cbfJNI.java".
  set(_java_files_generated
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/CBF_NODETYPE.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_FILE.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_cbf_context.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_cbf_file.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_double.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_int.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_long.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_p__cbf_handle_struct.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_p_cbf_node_struct.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_p_char.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_size_t.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_unsigned_int.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/SWIGTYPE_p_void.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/cbf.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/cbfConstants.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/cbfJNI.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/cbf_handle_struct.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/cbf_node.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/doubleP.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/intP.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/sizetP.java"
    "${CMAKE_CURRENT_BINARY_DIR}/jcbf/uintP.java")

  add_jar(cbflib
    "${_java_files_generated}"
    VERSION "${PROJECT_VERSION}")
  add_dependencies(cbflib cbf_wrap)
endif()


#
# Python bindings
if(CBF_ENABLE_PYTHON)
  # Want links (not lynx) to reduce the diffs against CBFlib.txt from
  # GitHub.  Makefile only uses links.  Need SWIG 4.0.0 or later.  For
  # Python 3, Makefile also adds "# coding=utf-8" to the top of
  # _wrapper.py.
  find_program(BROWSER_DUMP_TOOL NAMES links lynx elinks)
  find_package(Python COMPONENTS Development Interpreter REQUIRED)
  find_package(SWIG REQUIRED)
  include(UseSWIG)


  # Copy __init__.py and utils.py from ${CMAKE_CURRENT_SOURCE_DIR}.
  # This is not strictly necessary, but allows the module to be
  # imported from the build directory.
  add_custom_command(
    OUTPUT "${CMAKE_CURRENT_BINARY_DIR}/pycbf/__init__.py"
    COMMAND ${CMAKE_COMMAND} -E copy_if_different
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/__init__.py"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf")
  add_custom_command(
    OUTPUT "${CMAKE_CURRENT_BINARY_DIR}/pycbf/utils.py"
    COMMAND ${CMAKE_COMMAND} -E copy_if_different
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/utils.py"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf")

  add_custom_command(
    OUTPUT "${CMAKE_CURRENT_BINARY_DIR}/pycbf/CBFlib.txt"
    COMMAND ${BROWSER_DUMP_TOOL} -dump
      "${CMAKE_CURRENT_SOURCE_DIR}/doc/CBFlib.html" >
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/CBFlib.txt"
    DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/doc/CBFlib.html"
    WORKING_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/pycbf")


  # Generate the SWIG interfaces from CBFlib.txt (so really no need to
  # keep those under version control).
  add_custom_command(
    OUTPUT
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfdetectorwrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfgenericwrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfgoniometerwrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfhandlewrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfpositionerwrappers.i"
    COMMAND Python::Interpreter
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/make_pycbf.py"
      -o "${CMAKE_CURRENT_BINARY_DIR}/pycbf"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/CBFlib.txt"
    DEPENDS "${CMAKE_CURRENT_BINARY_DIR}/pycbf/CBFlib.txt")


  # What about SOVERSION?  Mebbe set VERSION as in java.  Depend on
  # __init__.py and utils.py only to ensure the files are copied.
  set_property(SOURCE "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf.i" PROPERTY
    DEPENDS
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfdetectorwrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfgenericwrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfgoniometerwrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/cbfhandlewrappers.i"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/__init__.py"
      "${CMAKE_CURRENT_BINARY_DIR}/pycbf/utils.py")
  swig_add_library(pycbf
    SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf.i"
    LANGUAGE Python
    OUTPUT_DIR "${CMAKE_CURRENT_BINARY_DIR}/pycbf")
  set_target_properties(pycbf PROPERTIES
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/pycbf")
  #target_compile_definitions(pycbf
  #  PRIVATE CBF_NO_REGEX) # From DIALS's build.py
  target_link_libraries(pycbf
    CBF
    Python::Module)


  # XXX Also install drel_lex.py, drel_yacc.py, drelc.py, and
  # drel_prep.py into bin?  Does the pycbf target properly include
  # _pycbf.so and _wrapper.py?
  install(
    FILES
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/__init__.py"
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/utils.py"
    COMPONENT "Runtime"
    DESTINATION "${Python_SITEARCH}")
  install(
    TARGETS pycbf
    COMPONENT "Runtime"
    DESTINATION "${Python_SITEARCH}")
endif()


#
# Build and install C and C++ examples.  Some of them are probably
# only useful for testing CBFlib.

# Not in 0.9.7
# add_executable(convert_f90_swig_wrap
#   "${EXAMPLES}/convert_f90_swig_wrap.cpp")

add_executable(convert_image
  "${EXAMPLES}/convert_image.c")
target_link_libraries(convert_image
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(convert_image PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(convert_minicbf
  "${EXAMPLES}/convert_minicbf.c")
target_link_libraries(convert_minicbf
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(convert_minicbf PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(makecbf
  "${EXAMPLES}/makecbf.c")
target_link_libraries(makecbf
  CBF)

add_executable(adscimg2cbf
  "${EXAMPLES}/adscimg2cbf.c"
  "${EXAMPLES}/adscimg2cbf_sub.c")
target_link_libraries(adscimg2cbf
  CBF
  "${libm}")

add_executable(cbf2adscimg
  "${EXAMPLES}/cbf2adscimg.c"
  "${EXAMPLES}/cbf2adscimg_sub.c")
target_link_libraries(cbf2adscimg
  CBF)

add_executable(cbf_standardize_numbers
  "${EXAMPLES}/cbf_standardize_numbers.c")
target_link_libraries(cbf_standardize_numbers
  CBF
  "${libm}")
if(NOT HAVE_FGETLN)
  target_sources(cbf_standardize_numbers PRIVATE "${SRC}/fgetln.c")
endif()

add_executable(changtestcompression
  "${EXAMPLES}/changtestcompression.c")
target_link_libraries(changtestcompression
  CBF
  "${libm}")

add_executable(img2cif
  "${EXAMPLES}/img2cif.c")
target_link_libraries(img2cif
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(img2cif PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(cif2cbf
  "${EXAMPLES}/cif2cbf.c")
target_link_libraries(cif2cbf
  CBF)
# CQR "${libm}") # Only in 0.9.8 and later
if(NOT HAVE_MKSTEMP)
  target_sources(cif2cbf PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(cbf2nexus
  "${EXAMPLES}/cbf2nexus.c")
target_link_libraries(cbf2nexus
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(cbf2nexus PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(minicbf2nexus
  "${EXAMPLES}/minicbf2nexus.c")
target_link_libraries(minicbf2nexus
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(minicbf2nexus PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(nexus2cbf
  "${EXAMPLES}/nexus2cbf.c")
target_link_libraries(nexus2cbf
  CBF)

add_executable(roi_peaksearch
  "${EXAMPLES}/roi_peaksearch.c"
  "${EXAMPLES}/dps_peaksearch.c")
target_link_libraries(roi_peaksearch
  CBF
  "${libm}")

add_executable(cbf_template_t
  "${EXAMPLES}/dectris_cbf_template_test/cbf_template_t.c")

add_executable(testcell
  "${EXAMPLES}/testcell.C")
target_link_libraries(testcell
  CBF)

add_executable(cif2c
  "${EXAMPLES}/cif2c.c")
target_link_libraries(cif2c
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(cif2c PRIVATE "${SRC}/mkstemp.c")
endif()

add_executable(sauter_test
  "${EXAMPLES}/sauter_test.C")
target_link_libraries(sauter_test
  CBF)

add_executable(sequence_match
  "${EXAMPLES}/sequence_match.c")
target_link_libraries(sequence_match
  CBF)
if(NOT HAVE_MKSTEMP)
  target_sources(sequence_match PRIVATE "${SRC}/mkstemp.c")
endif()

# Not in 0.9.7
# add_executable(cbf2tiff
#   "${EXAMPLES}/cbf2tiff.c")
# target_link_libraries(cbf2tiff
#   CBF
#   tiff)

add_executable(tiff2cbf
  "${EXAMPLES}/tiff2cbf.c"
  "${EXAMPLES}/tif_sprint.c")
target_link_libraries(tiff2cbf
  CBF
  tiff)

add_executable(arvai_test
  "${EXAMPLES}/arvai_test.c")
target_link_libraries(arvai_test
  CBF)

add_executable(testreals
  "${EXAMPLES}/testreals.c")
target_link_libraries(testreals
  CBF)

add_executable(testflat
  "${EXAMPLES}/testflat.c")
target_link_libraries(testflat
  CBF)

add_executable(testflatpacked
  "${EXAMPLES}/testflatpacked.c")
target_link_libraries(testflatpacked
  CBF)

if(CBF_ENABLE_JAVA)
  add_executable(ctestcbf
    "${EXAMPLES}/testcbf.c")
  target_link_libraries(ctestcbf
    CBF)

  add_jar(testcbf
    "${EXAMPLES}/testcbf.java"
    INCLUDE_JARS cbflib)
endif()

if(CBF_ENABLE_ULP)
  add_executable(testulp
    "${EXAMPLES}/testulp.c")
  target_link_libraries(testulp
    CBF)
endif()

add_executable(testhdf5
  "${EXAMPLES}/testhdf5.c")
target_link_libraries(testhdf5
  CBF)

add_executable(testalloc
  "${EXAMPLES}/testalloc.c")
target_link_libraries(testalloc
  CBF)

add_executable(test_cbf_airy_disk
  "${EXAMPLES}/test_cbf_airy_disk.c")
target_link_libraries(test_cbf_airy_disk
  CBF
  "${libm}")

add_executable(cbf_testxfelread
  "${EXAMPLES}/cbf_testxfelread.c")
target_link_libraries(cbf_testxfelread
  CBF
  "${libm}")

add_executable(cbf_tail
  "${EXAMPLES}/cbf_tail.c")

install(
  TARGETS
    makecbf
    img2cif
    cif2cbf
    adscimg2cbf
    cbf2adscimg
    changtestcompression
    convert_image
    convert_minicbf
    minicbf2nexus
    cbf2nexus
    nexus2cbf
    cbf_template_t
    testcell
    sauter_test
    sequence_match
    tiff2cbf
  COMPONENT "Examples")


#
# F90 examples.  Only for testing, not installed.  Makefile orders
# these with the above.
if(CBF_ENABLE_FORTRAN)
  add_executable(test_fcb_read_image
    "${CMAKE_CURRENT_BINARY_DIR}/src/test_fcb_read_image.f90")
  target_link_libraries(test_fcb_read_image
    FCB)

  add_executable(test_xds_binary
    "${CMAKE_CURRENT_BINARY_DIR}/src/test_xds_binary.f90")
  target_link_libraries(test_xds_binary
    HDF5
    FCB)
endif()


#
# tests
enable_testing()

# Path to the valgrind executable
find_program(VALGRIND valgrind)
if(VALGRIND)
  set(VALGRIND_COMMAND ${VALGRIND} --error-exitcode=3 --leak-check=full)
else ()
  set(VALGRIND_COMMAND "")
endif ()

# Set up a wrapper to call 'h5dump' and redirect its output to a file.
file(GENERATE
  OUTPUT "h5dump-$<CONFIG>.cmake"
  INPUT "h5dump.cmake")


#
# img2cif/cif2cbf
#
# Converting to canonical CBF via flatpacked CIF is identical to
# direct conversion.
add_test(NAME img2cif-flatpacked-cif
  COMMAND img2cif -c flatpacked -m headers -d digest -e base64
    "${CBF_DATA_INPUT}/example.mar2300"
    "img2cif_packed.cif")
set_tests_properties(img2cif-flatpacked-cif PROPERTIES
  FIXTURES_SETUP img2cif-flatpacked-cif
  REQUIRED_FILES "${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME cif2cbf-canonical-cbf
  COMMAND cif2cbf -e none -c canonical
    "img2cif_packed.cif"
    "cif2cbf_canonical.cbf")
set_tests_properties(cif2cbf-canonical-cbf PROPERTIES
  FIXTURES_REQUIRED img2cif-flatpacked-cif
  FIXTURES_SETUP cif2cbf-canonical-cbf)

add_test(NAME img2cif-canonical-cbf
  COMMAND img2cif -c canonical -m headers -d digest -e none
    "${CBF_DATA_INPUT}/example.mar2300"
    "img2cif_canonical.cbf")
set_tests_properties(img2cif-canonical-cbf PROPERTIES
  FIXTURES_SETUP img2cif-canonical-cbf
  REQUIRED_FILES "${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME cif2cbf-img2cif-canonical-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "cif2cbf_canonical.cbf"
    "img2cif_canonical.cbf")
set_tests_properties(cif2cbf-img2cif-canonical-cmp PROPERTIES
  FIXTURES_REQURIED "img2cif-canonical-cbf;cif2cbf-canonical-cbf")

add_test(NAME img2cif-flatpacked-cif-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "img2cif_packed.cif")
set_tests_properties(img2cif-flatpacked-cif-cleanup PROPERTIES
  FIXTURES_CLEANUP img2cif-flatpacked-cif)

add_test(NAME cif2cbf-canonical-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "cif2cbf_canonical.cbf")
set_tests_properties(cif2cbf-canonical-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP img2cif-canonical-cbf)

add_test(NAME img2cif-canonical-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "img2cif_canonical.cbf")
set_tests_properties(img2cif-canonical-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP img2cif-canonical-cbf)


#
# img2cif/cif2cbf
#
# Converting to flatpacked CBF via canonical CIF is identical to
# direct conversion.
add_test(NAME img2cif-canonical-cif
  COMMAND img2cif -c canonical -m headers -d digest -e base64
    "${CBF_DATA_INPUT}/example.mar2300"
    "img2cif_canonical.cif")
set_tests_properties(img2cif-canonical-cif PROPERTIES
  FIXTURES_SETUP img2cif-canonical-cif
  REQUIRED_FILES "${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME cif2cbf-flatpacked-cbf
  COMMAND cif2cbf -e none -c flatpacked
    "img2cif_canonical.cif"
    "cif2cbf_packed.cbf")
set_tests_properties(cif2cbf-flatpacked-cbf PROPERTIES
  FIXTURES_REQURIED img2cif-canonical-cif
  FIXTURES_SETUP cif2cbf-flatpacked-cbf)

add_test(NAME img2cif-flatpacked-cbf
  COMMAND img2cif -c flatpacked -m headers -d digest -e none
    "${CBF_DATA_INPUT}/example.mar2300"
    "img2cif_packed.cbf")
set_tests_properties(img2cif-flatpacked-cbf PROPERTIES
  FIXTURES_SETUP img2cif-flatpacked-cbf
  REQUIRED_FILES "${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME cif2cbf-img2cif-flatpacked-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "cif2cbf_packed.cbf"
    "img2cif_packed.cbf")
set_tests_properties(cif2cbf-img2cif-flatpacked-cmp PROPERTIES
  FIXTURES_REQURIED "img2cif-flatpacked-cbf;cif2cbf-flatpacked-cbf")

add_test(NAME img2cif-canonical-cif-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "img2cif_canonical.cif")
set_tests_properties(img2cif-canonical-cif-cleanup PROPERTIES
  FIXTURES_CLEANUP img2cif-canonical-cif)

add_test(NAME cif2cbf-flatpacked-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "cif2cbf_packed.cbf")
set_tests_properties(cif2cbf-flatpacked-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-flatpacked-cbf)

add_test(NAME img2cif-flatpacked-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "img2cif_packed.cbf")
set_tests_properties(img2cif-flatpacked-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP img2cif-flatpacked-cbf)


#
# makecbf
add_test(NAME makecbf
  COMMAND makecbf
    "${CBF_DATA_INPUT}/example.mar2300"
    "makecbf.cbf")
set_tests_properties(makecbf PROPERTIES
  FIXTURES_SETUP "makecbf"
  REQUIRED_FILES "${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME makecbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "cif2cbf_packed.cbf"
    "makecbf.cbf")
set_tests_properties(makecbf-cmp PROPERTIES
  FIXTURES_REQUIRED "cif2cbf-flatpacked-cbf;makecbf")

add_test(NAME makecbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "makecbf.cbf")
set_tests_properties(makecbf-cleanup PROPERTIES
  FIXTURES_CLEANUP makecbf)


#
# Extra Tests

#
# cif2cbf
#
# Roundtrip makecbf.cbf via cif2cbf_ehcn.cif.
add_test(NAME cif2cbf-ehcn
  COMMAND cif2cbf -e hex -c none
    "makecbf.cbf"
    "cif2cbf_ehcn.cif")
set_tests_properties(cif2cbf-ehcn PROPERTIES
  FIXTURES_REQUIRED makecbf
  FIXTURES_SETUP cif2cbf-ehcn)

add_test(NAME cif2cbf-ehcn-encp
  COMMAND cif2cbf -e none -c flatpacked
    "cif2cbf_ehcn.cif"
    "cif2cbf_encp.cbf")
set_tests_properties(cif2cbf-ehcn-encp PROPERTIES
  FIXTURES_REQUIRED cif2cbf-ehcn
  FIXTURES_SETUP cif2cbf-ehcn-encp)

add_test(NAME cif2cbf-ehcn-encp-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "makecbf.cbf"
    "cif2cbf_encp.cbf")
set_tests_properties(cif2cbf-ehcn-encp-cmp PROPERTIES
  FIXTURES_REQUIRED "makecbf;cif2cbf-ehcn-encp")

add_test(NAME cif2cbf-ehcn-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "cif2cbf_ehcn.cif")
set_tests_properties(cif2cbf-ehcn-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-ehcn)

add_test(NAME cif2cbf-ehcn-encp-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "cif2cbf_encp.cbf")
set_tests_properties(cif2cbf-ehcn-encp-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-ehcn-encp)


#
# 9ins
add_test(NAME cif2cbf-9ins
  COMMAND cif2cbf
    -i "${CBF_DATA_INPUT}/9ins.cif"
    -o "9ins.cbf")
set_tests_properties(cif2cbf-9ins PROPERTIES
  FIXTURES_SETUP 9ins
  REQUIRED_FILES "${CBF_DATA_INPUT}/9ins.cif")

add_test(NAME cif2cbf-9ins-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_INPUT}/9ins.cif"
    "9ins.cbf")
set_tests_properties(cif2cbf-9ins-cmp PROPERTIES
  FIXTURES_REQUIRED 9ins
  REQUIRED_FILES "${CBF_DATA_INPUT}/9ins.cif")

add_test(NAME cif2cbf-9ins-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "9ins.cbf")
set_tests_properties(cif2cbf-9ins-cleanup PROPERTIES
  FIXTURES_CLEANUP 9ins)


#
# convert_image-flat
add_test(NAME convert_image-flat
  COMMAND convert_image
    -p "${TEMPLATES}/template_mar345_2300x2300.cbf"
    -F "${CBF_DATA_INPUT}/example.mar2300"
    "converted_flat.cbf")
set_tests_properties(convert_image-flat PROPERTIES
  FIXTURES_SETUP convert_image-flat
  REQUIRED_FILES "${TEMPLATES}/template_mar345_2300x2300.cbf;${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME convert_image-flat-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/converted_flat_orig.cbf"
    "converted_flat.cbf")
set_tests_properties(convert_image-flat-cmp PROPERTIES
  FIXTURES_REQUIRED convert_image-flat
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/converted_flat_orig.cbf")

add_test(NAME convert_image-flat-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "converted_flat.cbf")
set_tests_properties(convert_image-flat-cleanup PROPERTIES
  FIXTURES_CLEANUP convert_image-flat)


#
# convert_image
add_test(NAME convert_image
  COMMAND convert_image -p "${TEMPLATES}/template_mar345_2300x2300.cbf"
    "${CBF_DATA_INPUT}/example.mar2300"
    "converted.cbf")
set_tests_properties(convert_image PROPERTIES
  FIXTURES_SETUP convert_image
  REQUIRED_FILES "${TEMPLATES}/template_mar345_2300x2300.cbf;${CBF_DATA_INPUT}/example.mar2300")

add_test(NAME convert_image-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/converted_orig.cbf"
    "converted.cbf")
set_tests_properties(convert_image-cmp PROPERTIES
  FIXTURES_REQUIRED convert_image
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/converted_orig.cbf")

add_test(NAME convert_image-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "converted.cbf")
set_tests_properties(convert_image-cleanup PROPERTIES
  FIXTURES_CLEANUP convert_image)


#
# testcell
add_test(NAME testcell
  COMMAND ${CMAKE_COMMAND}
    "-Dcommand=$<TARGET_FILE:testcell>"
    "-Dinput-file=${CMAKE_CURRENT_SOURCE_DIR}/testcell.dat"
    "-Doutput-file=testcell.prt"
    -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
set_tests_properties(testcell PROPERTIES
  FIXTURES_SETUP testcell
  REQUIRED_FILES "${CMAKE_CURRENT_SOURCE_DIR}/testcell.dat")

add_test(NAME testcell-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files --ignore-eol
    "${CBF_DATA_OUTPUT}/testcell_orig.prt"
    "testcell.prt")
set_tests_properties(testcell-cmp PROPERTIES
  FIXTURES_REQUIRED testcell
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/testcell_orig.prt")

add_test(NAME testcell-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testcell.prt")
set_tests_properties(testcell-cleanup PROPERTIES
  FIXTURES_CLEANUP testcell)


#
# convert_image-adscimg-flat
add_test(NAME convert_image-adscimg-flat
  COMMAND convert_image
    -p "${TEMPLATES}/template_adscquantum315_3072x3072.cbf"
    -F -d adscquantum315
    "${CBF_DATA_INPUT}/mb_LP_1_001.img"
    "adscconverted_flat.cbf")
set_tests_properties(convert_image-adscimg-flat PROPERTIES
  FIXTURES_SETUP convert_image-adscimg-flat
  REQUIRED_FILES "${TEMPLATES}/template_adscquantum315_3072x3072.cbf;${CBF_DATA_INPUT}/mb_LP_1_001.img")

add_test(NAME convert_image-adscimg-flat-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/adscconverted_flat_orig.cbf"
    "adscconverted_flat.cbf")
set_tests_properties(convert_image-adscimg-flat-cmp PROPERTIES
  FIXTURES_REQUIRED convert_image-adscimg-flat
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/adscconverted_flat_orig.cbf")

add_test(NAME convert_image-adscimg-flat-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "adscconverted_flat.cbf")
set_tests_properties(convert_image-adscimg-flat-cleanup PROPERTIES
  FIXTURES_CLEANUP convert_image-adscimg-flat)


#
# convert_image-adscimg
add_test(NAME convert_image-adscimg
  COMMAND convert_image
    -p "${TEMPLATES}/template_adscquantum315_3072x3072.cbf"
    -d adscquantum315
    "${CBF_DATA_INPUT}/mb_LP_1_001.img"
    "adscconverted.cbf")
set_tests_properties(convert_image-adscimg PROPERTIES
  FIXTURES_SETUP convert_image-adscimg
  REQUIRED_FILES "${TEMPLATES}/template_adscquantum315_3072x3072.cbf;${CBF_DATA_INPUT}/mb_LP_1_001.img")

add_test(NAME convert_image-adscimg-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/adscconverted_orig.cbf"
    "adscconverted.cbf")
set_tests_properties(convert_image-adscimg-cmp PROPERTIES
  FIXTURES_REQUIRED convert_image-adscimg
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/adscconverted_orig.cbf")

add_test(NAME convert_image-adscimg-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "adscconverted.cbf")
set_tests_properties(convert_image-adscimg-cleanup PROPERTIES
  FIXTURES_CLEANUP convert_image-adscimg)


#
# adscimg2cbf
#
# Use a different output name in adscimg2cbf-setup to avoid racing
# with convert_image-adscimg.
add_test(NAME adscimg2cbf-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${CBF_DATA_INPUT}/mb_LP_1_001.img"
    "${CMAKE_CURRENT_BINARY_DIR}/mb_LP_1_001-adscimg2cbf.img")
set_tests_properties(adscimg2cbf-setup PROPERTIES
  FIXTURES_SETUP adscimg2cbf-setup
  REQUIRED_FILES "${CBF_DATA_INPUT}/mb_LP_1_001.img")

add_test(NAME adscimg2cbf
  COMMAND adscimg2cbf --no_pad --cbf_packed,flat "mb_LP_1_001-adscimg2cbf.img")
set_tests_properties(adscimg2cbf PROPERTIES
  FIXTURES_REQUIRED adscimg2cbf-setup
  FIXTURES_SETUP adscimg2cbf)

add_test(NAME adscimg2cbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/mb_LP_1_001_orig.cbf"
    "mb_LP_1_001-adscimg2cbf.cbf")
set_tests_properties(adscimg2cbf-cmp PROPERTIES
  FIXTURES_REQUIRED adscimg2cbf
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/mb_LP_1_001_orig.cbf")

add_test(NAME adscimg2cbf-setup-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "mb_LP_1_001-adscimg2cbf.img")
set_tests_properties(adscimg2cbf-setup-cleanup PROPERTIES
  FIXTURES_CLEANUP adscimg2cbf-setup)

add_test(NAME adscimg2cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "mb_LP_1_001-adscimg2cbf.cbf")
set_tests_properties(adscimg2cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP adscimg2cbf)


#
# cbf2adscimg
add_test(NAME cbf2adscimg
  COMMAND cbf2adscimg "mb_LP_1_001-adscimg2cbf.cbf")
set_tests_properties(cbf2adscimg PROPERTIES
  FIXTURES_REQUIRED adscimg2cbf
  FIXTURES_SETUP cbf2adscimg)

add_test(NAME cbf2adscimg-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_INPUT}/mb_LP_1_001.img"
    "mb_LP_1_001-adscimg2cbf.img")
set_tests_properties(cbf2adscimg-cmp PROPERTIES
  FIXTURES_REQUIRED cbf2adscimg
  REQUIRED_FILES "${CBF_DATA_INPUT}/mb_LP_1_001.img")

add_test(NAME cbf2adscimg-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "mb_LP_1_001-adscimg2cbf.img")
set_tests_properties(cbf2adscimg-cleanup PROPERTIES
  FIXTURES_CLEANUP adscimg2cbf)


#
# batch_convert_minicbf
add_test(NAME batch_convert_minicbf
  COMMAND ${CMAKE_COMMAND}
    "-DCBF_CONVERT_MINICBF_PATH=$<TARGET_FILE_DIR:convert_minicbf>"
    -P "${CMAKE_CURRENT_SOURCE_DIR}/examples/batch_convert_minicbf.cmake" --
      "${CBF_DATA_INPUT}"
      "${CMAKE_CURRENT_BINARY_DIR}"
      "X4_lots_M1S4_1_*.cbf"
      "${TEMPLATES}/template_X4_lots_M1S4.cbf")
set_tests_properties(batch_convert_minicbf PROPERTIES
  FIXTURES_SETUP batch_convert_minicbf)

add_test(NAME batch_convert_minicbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm
    "X4_lots_M1S4_1_0001.cbf"
    "X4_lots_M1S4_1_0002.cbf"
    "X4_lots_M1S4_1_0003.cbf"
    "X4_lots_M1S4_1_0004.cbf"
    "X4_lots_M1S4_1_0005.cbf")
set_tests_properties(batch_convert_minicbf-cleanup PROPERTIES
  FIXTURES_CLEANUP batch_convert_minicbf)


#
# convert_minicbf-v1
add_test(NAME convert_minicbf-v1
  COMMAND convert_minicbf
    -p "${TEMPLATES}/template_pilatus6m_2463x2527.cbf" -d pilatus6m -v 1
    "${CBF_DATA_INPUT}/insulin_pilatus6m.cbf"
    "insulin_pilatus6mconverted.cbf")
set_tests_properties(convert_minicbf-v1 PROPERTIES
  FIXTURES_SETUP convert_minicbf-v1
  REQUIRED_FILES "${CBF_DATA_INPUT}/insulin_pilatus6m.cbf")

add_test(NAME convert_minicbf-v1-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/insulin_pilatus6mconverted_orig.cbf"
    "insulin_pilatus6mconverted.cbf")
set_tests_properties(convert_minicbf-v1-cmp PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/insulin_pilatus6mconverted_orig.cbf")

add_test(NAME convert_minicbf-v1-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted.cbf")
set_tests_properties(convert_minicbf-v1-cleanup PROPERTIES
  FIXTURES_CLEANUP convert_minicbf-v1)


#
# convert_minicbf
add_test(NAME convert_minicbf
  COMMAND convert_minicbf
    -p "${TEMPLATES}/template_pilatus6m_2463x2527.cbf" -d pilatus6m
    "${CBF_DATA_INPUT}/insulin_pilatus6m.cbf"
    "insulin_pilatus6mconverted_v2.cbf")
set_tests_properties(convert_minicbf PROPERTIES
  FIXTURES_SETUP convert_minicbf
  REQUIRED_FILES "${CBF_DATA_INPUT}/insulin_pilatus6m.cbf")

add_test(NAME convert_minicbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/insulin_pilatus6mconverted_v2_orig.cbf"
    "insulin_pilatus6mconverted_v2.cbf")
set_tests_properties(convert_minicbf-cmp PROPERTIES
  FIXTURES_REQUIRED convert_minicbf
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/insulin_pilatus6mconverted_v2_orig.cbf")

add_test(NAME convert_minicbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_v2.cbf")
set_tests_properties(convert_minicbf-cleanup PROPERTIES
  FIXTURES_CLEANUP convert_minicbf)


#
# check the default as hdf5 dumps
#
# This is used for comparison.
add_test(NAME insulin-orig-dump
  COMMAND ${CMAKE_COMMAND}
    "-Dinput-file=${CBF_DATA_OUTPUT}/insulin_pilatus6mconverted_orig.cbf.h5"
    "-Doutput-file=insulin_pilatus6mconverted_orig.cbf.h5.dump"
    -P "${PROJECT_BINARY_DIR}/h5dump-$<CONFIG>.cmake")
set_tests_properties(insulin-orig-dump PROPERTIES
  FIXTURES_SETUP insulin-orig-dump
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/insulin_pilatus6mconverted_orig.cbf.h5")

add_test(NAME insulin-orig-dump-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_orig.cbf.h5.dump")
set_tests_properties(insulin-orig-dump-cleanup PROPERTIES
  FIXTURES_CLEANUP insulin-orig-dump)


#
# cif2cbf-opaque
#
# cif2cbf basic round-trip to hdf5 tests
#
# Starting with insulin_pilatus6mconverted.cbf, create hdf5 files
# using opaque, encI, encp, encb, encc, encz.
add_test(NAME cif2cbf-opaque
  COMMAND cif2cbf -5 w ${HDF5REGISTER} -O
    -i "insulin_pilatus6mconverted.cbf"
    -o "insulin_pilatus6mconverted.cbf.h5")
set_tests_properties(cif2cbf-opaque PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  FIXTURES_SETUP cif2cbf-opaque)

add_test(NAME cif2cbf-opaque-dump
  COMMAND ${CMAKE_COMMAND}
    "-Dinput-file=insulin_pilatus6mconverted.cbf.h5"
    "-Doutput-file=insulin_pilatus6mconverted.cbf.h5.dump"
    -P "${PROJECT_BINARY_DIR}/h5dump-$<CONFIG>.cmake")
set_tests_properties(cif2cbf-opaque-dump PROPERTIES
  FIXTURES_REQUIRED cif2cbf-opaque
  FIXTURES_SETUP cif2cbf-opaque-dump)

add_test(NAME cif2cbf-opaque-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "insulin_pilatus6mconverted_orig.cbf.h5.dump"
    "insulin_pilatus6mconverted.cbf.h5.dump")
set_tests_properties(cif2cbf-opaque-cmp PROPERTIES
  FIXTURES_REQUIRED "insulin-orig-dump;cif2cbf-opaque-dump")

add_test(NAME cif2cbf-opaque-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted.cbf.h5")
set_tests_properties(cif2cbf-opaque-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-opaque)

add_test(NAME cif2cbf-opaque-dump-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted.cbf.h5.dump")
set_tests_properties(cif2cbf-opaque-dump-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-opaque-dump)


#
# cif2cbf-encI
#
# cif2cbf round-trip tests
#
# Convert each of the non-opaque h5 files to encI (was encp in old
# CMakeLists.txt) CBFs and compare them.  The Makefile writes
# everything to insulin_pilatus6mconverted_encI.cbf.h5.cbf.
add_test(NAME cif2cbf-encI
  COMMAND cif2cbf -5 w ${HDF5REGISTER} -en -cI
    -i "insulin_pilatus6mconverted.cbf"
    -o "insulin_pilatus6mconverted_encI.cbf.h5")
set_tests_properties(cif2cbf-encI PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  FIXTURES_SETUP cif2cbf-encI)

add_test(NAME cif2cbf-encI-cbf
  COMMAND cif2cbf -5 rn ${HDF5REGISTER} -en -cI
    -i "insulin_pilatus6mconverted_encI.cbf.h5"
    -o "insulin_pilatus6mconverted_encI.cbf.h5.cbf")
set_tests_properties(cif2cbf-encI-cbf PROPERTIES
  FIXTURES_REQUIRED cif2cbf-encI
  FIXTURES_SETUP cif2cbf-encI-cbf)

add_test(NAME cif2cbf-encI-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encI.cbf.h5")
set_tests_properties(cif2cbf-encI-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encI)

add_test(NAME cif2cbf-encI-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encI.cbf.h5.cbf")
set_tests_properties(cif2cbf-encI-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encI-cbf)


#
# cif2cbf-encp
add_test(NAME cif2cbf-encp
  COMMAND cif2cbf -5 w ${HDF5REGISTER} -en -cp
    -i "insulin_pilatus6mconverted.cbf"
    -o "insulin_pilatus6mconverted_encp.cbf.h5")
set_tests_properties(cif2cbf-encp PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  FIXTURES_SETUP cif2cbf-encp)

add_test(NAME cif2cbf-encp-cbf
  COMMAND cif2cbf -5 rn ${HDF5REGISTER} -en -cI
    -i "insulin_pilatus6mconverted_encp.cbf.h5"
    -o "insulin_pilatus6mconverted_encp.cbf.h5.cbf")
set_tests_properties(cif2cbf-encp-cbf PROPERTIES
  FIXTURES_REQUIRED cif2cbf-encp
  FIXTURES_SETUP cif2cbf-encp-cbf)

add_test(NAME cif2cbf-encp-cbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "insulin_pilatus6mconverted_encI.cbf.h5.cbf"
    "insulin_pilatus6mconverted_encp.cbf.h5.cbf")
set_tests_properties(cif2cbf-encp-cbf-cmp PROPERTIES
  FIXTURES_REQUIRED "cif2cbf-encI-cbf;cif2cbf-encp-cbf")

add_test(NAME cif2cbf-encp-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encp.cbf.h5")
set_tests_properties(cif2cbf-encp-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encp)

add_test(NAME cif2cbf-encp-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encp.cbf.h5.cbf")
set_tests_properties(cif2cbf-encp-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encp-cbf)


#
# cif2cbf-encb
add_test(NAME cif2cbf-encb
  COMMAND cif2cbf -5 w ${HDF5REGISTER} -en -cb
    -i "insulin_pilatus6mconverted.cbf"
    -o "insulin_pilatus6mconverted_encb.cbf.h5")
set_tests_properties(cif2cbf-encb PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  FIXTURES_SETUP cif2cbf-encb)

add_test(NAME cif2cbf-encb-cbf
  COMMAND cif2cbf -5 rn ${HDF5REGISTER} -en -cI
    -i "insulin_pilatus6mconverted_encb.cbf.h5"
    -o "insulin_pilatus6mconverted_encb.cbf.h5.cbf")
set_tests_properties(cif2cbf-encb-cbf PROPERTIES
  FIXTURES_REQUIRED cif2cbf-encb
  FIXTURES_SETUP cif2cbf-encb-cbf)

add_test(NAME cif2cbf-encb-cbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "insulin_pilatus6mconverted_encI.cbf.h5.cbf"
    "insulin_pilatus6mconverted_encb.cbf.h5.cbf")
set_tests_properties(cif2cbf-encb-cbf-cmp PROPERTIES
  FIXTURES_REQUIRED "cif2cbf-encI-cbf;cif2cbf-encb-cbf")

add_test(NAME cif2cbf-encb-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encb.cbf.h5")
set_tests_properties(cif2cbf-encb-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encb)

add_test(NAME cif2cbf-encb-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encb.cbf.h5.cbf")
set_tests_properties(cif2cbf-encb-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encb-cbf)


#
# cif2cbf-encc
add_test(NAME cif2cbf-encc
  COMMAND cif2cbf -5 w ${HDF5REGISTER} -en -cc
    -i "insulin_pilatus6mconverted.cbf"
    -o "insulin_pilatus6mconverted_encc.cbf.h5")
set_tests_properties(cif2cbf-encc PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  FIXTURES_SETUP cif2cbf-encc)

add_test(NAME cif2cbf-encc-cbf
  COMMAND cif2cbf -5 rn ${HDF5REGISTER} -en -cI
    -i "insulin_pilatus6mconverted_encc.cbf.h5"
    -o "insulin_pilatus6mconverted_encc.cbf.h5.cbf")
set_tests_properties(cif2cbf-encc-cbf PROPERTIES
  FIXTURES_REQUIRED cif2cbf-encc
  FIXTURES_SETUP cif2cbf-encc-cbf)

add_test(NAME cif2cbf-encc-cbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "insulin_pilatus6mconverted_encI.cbf.h5.cbf"
    "insulin_pilatus6mconverted_encc.cbf.h5.cbf")
set_tests_properties(cif2cbf-encc-cbf-cmp PROPERTIES
  FIXTURES_REQUIRED "cif2cbf-encI-cbf;cif2cbf-encc-cbf")

add_test(NAME cif2cbf-encc-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encc.cbf.h5")
set_tests_properties(cif2cbf-encc-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encc)

add_test(NAME cif2cbf-encc-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encc.cbf.h5.cbf")
set_tests_properties(cif2cbf-encc-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encc-cbf)


#
# cif2cbf-encz
add_test(NAME cif2cbf-encz
  COMMAND cif2cbf -5 w ${HDF5REGISTER} -en -cz
    -i "insulin_pilatus6mconverted.cbf"
    -o "insulin_pilatus6mconverted_encz.cbf.h5")
set_tests_properties(cif2cbf-encz PROPERTIES
  FIXTURES_REQUIRED convert_minicbf-v1
  FIXTURES_SETUP cif2cbf-encz)

add_test(NAME cif2cbf-encz-cbf
  COMMAND cif2cbf -5 rn ${HDF5REGISTER} -en -cI
    -i "insulin_pilatus6mconverted_encz.cbf.h5"
    -o "insulin_pilatus6mconverted_encz.cbf.h5.cbf")
set_tests_properties(cif2cbf-encz-cbf PROPERTIES
  FIXTURES_REQUIRED cif2cbf-encz
  FIXTURES_SETUP cif2cbf-encz-cbf)

add_test(NAME cif2cbf-encz-cbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "insulin_pilatus6mconverted_encI.cbf.h5.cbf"
    "insulin_pilatus6mconverted_encz.cbf.h5.cbf")
set_tests_properties(cif2cbf-encz-cbf-cmp PROPERTIES
  FIXTURES_REQUIRED "cif2cbf-encI-cbf;cif2cbf-encz-cbf")

add_test(NAME cif2cbf-encz-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encz.cbf.h5")
set_tests_properties(cif2cbf-encz-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encz)

add_test(NAME cif2cbf-encz-cbf-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "insulin_pilatus6mconverted_encz.cbf.h5.cbf")
set_tests_properties(cif2cbf-encz-cbf-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-encz-cbf)


#
# test_cbf_airy_disk
add_test(NAME test_cbf_airy_disk
  COMMAND test_cbf_airy_disk)


#
# cbf_testxfelread
add_test(NAME xfelread-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${CMAKE_CURRENT_SOURCE_DIR}/idx-s00-20131106040304531.cbf"
    "${CMAKE_CURRENT_BINARY_DIR}")
set_tests_properties(xfelread-setup PROPERTIES
  FIXTURES_SETUP xfelread-setup)

add_test(NAME xfelread
  COMMAND cbf_testxfelread)
set_tests_properties(xfelread PROPERTIES
  FIXTURES_REQUIRED xfelread-setup
  FIXTURES_SETUP xfelread)

add_test(NAME xfelread-setup-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "idx-s00-20131106040304531.cbf")
set_tests_properties(xfelread-setup-cleanup PROPERTIES
  FIXTURES_CLEANUP xfelread-setup)

add_test(NAME xfelread-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "idx-s00-20131106040304531_flat.cbf")
set_tests_properties(xfelread-cleanup PROPERTIES
  FIXTURES_CLEANUP xfelread)


#
# testalloc
if(VALGRIND)
  add_test(NAME testalloc
    COMMAND ${VALGRIND_COMMAND} $<TARGET_FILE:testalloc>)
else()
  add_test(NAME testalloc
    COMMAND testalloc)
endif()


#
# testhdf5
add_test(NAME testhdf5
  COMMAND testhdf5)
set_tests_properties(testhdf5 PROPERTIES
  FIXTURES_SETUP testhdf5)

add_test(NAME testhdf5-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testfile.h5")
set_tests_properties(testhdf5-cleanup PROPERTIES
  FIXTURES_CLEANUP testhdf5)


#
# testulp
if(CBF_ENABLE_ULP)
  add_test(NAME testulp
    COMMAND testulp)
endif()


#
# minicbf2nexus
#
# Avoid file(GLOB ...) in source tree.
set(_minicbf2nexus_files
  "${CBF_DATA_INPUT}/X4_lots_M1S4_1_0001.cbf"
  "${CBF_DATA_INPUT}/X4_lots_M1S4_1_0002.cbf"
  "${CBF_DATA_INPUT}/X4_lots_M1S4_1_0003.cbf"
  "${CBF_DATA_INPUT}/X4_lots_M1S4_1_0004.cbf"
  "${CBF_DATA_INPUT}/X4_lots_M1S4_1_0005.cbf")
add_test(NAME minicbf2nexus
  COMMAND minicbf2nexus -c zlib
    -C "${CMAKE_CURRENT_SOURCE_DIR}/minicbf_test/config" ${HDF5REGISTER}
    -o "minicbf.h5"
    ${_minicbf2nexus_files})
set_tests_properties(minicbf2nexus PROPERTIES
  FIXTURES_SETUP minicbf2nexus
  REQUIRED_FILES ${_minicbf2nexus_files})

add_test(NAME minicbf2nexus-dump
  COMMAND ${CMAKE_COMMAND}
    "-Dinput-file=minicbf.h5"
    "-Doutput-file=minicbf.dump"
    -P "${PROJECT_BINARY_DIR}/h5dump-$<CONFIG>.cmake")
set_tests_properties(minicbf2nexus-dump PROPERTIES
  FIXTURES_REQUIRED minicbf2nexus
  FIXTURES_SETUP minicbf2nexus-dump)

add_test(NAME minicbf2nexus-original
  COMMAND ${CMAKE_COMMAND}
  "-Dinput-file=${CBF_DATA_OUTPUT}/minicbf_orig.h5"
  "-Doutput-file=minicbf_original.dump"
  -P "${PROJECT_BINARY_DIR}/h5dump-$<CONFIG>.cmake")
set_tests_properties(minicbf2nexus-original PROPERTIES
  FIXTURES_SETUP minicbf2nexus-original
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/minicbf_orig.h5")

add_test(NAME minicbf2nexus-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "minicbf_original.dump"
    "minicbf.dump")
set_tests_properties(minicbf2nexus-cmp PROPERTIES
  FIXTURES_REQUIRED "minicbf2nexus-dump;minicbf2nexus-original")

add_test(NAME minicbf2nexus-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "minicbf.h5")
set_tests_properties(minicbf2nexus-cleanup PROPERTIES
  FIXTURES_CLEANUP minicbf2nexus)

add_test(NAME minicbf2nexus-dump-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "minicbf.dump")
set_tests_properties(minicbf2nexus-dump-cleanup PROPERTIES
  FIXTURES_CLEANUP minicbf2nexus-dump)

add_test(NAME minicbf2nexus-original-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "minicbf_original.dump")
set_tests_properties(minicbf2nexus-original-cleanup PROPERTIES
  FIXTURES_CLEANUP minicbf2nexus-original)


#
# cbf2nexus & nexus2cbf
#
# Round-trip cbf2nexus and nexus2cbf tests using i19 data (was i03
# data in old CMakeLists.txt).
add_test(NAME cbf2nexus-1
  COMMAND cbf2nexus -c zlib --list
    -o "i19-1.h5"
    "${CBF_DATA_INPUT}/1191_00005.cbf")
set_tests_properties(cbf2nexus-1 PROPERTIES
  FIXTURES_SETUP cbf2nexus-1
  REQUIRED_FILES "${CBF_DATA_INPUT}/1191_00005.cbf")

add_test(NAME nexus2cbf-1
  COMMAND nexus2cbf
    -o "i19-1.cbf"
    "i19-1.h5")
set_tests_properties(nexus2cbf-1 PROPERTIES
  FIXTURES_REQUIRED cbf2nexus-1
  FIXTURES_SETUP nexus2cbf-1)

add_test(NAME cbf2nexus-2
  COMMAND cbf2nexus -c zlib --list
    -o "i19-2.h5"
    "i19-1.cbf")
set_tests_properties(cbf2nexus-2 PROPERTIES
  FIXTURES_REQUIRED nexus2cbf-1
  FIXTURES_SETUP cbf2nexus-2)

add_test(NAME nexus2cbf-2
  COMMAND nexus2cbf
    -o "i19-2.cbf"
    "i19-2.h5")
set_tests_properties(nexus2cbf-2 PROPERTIES
  FIXTURES_REQUIRED cbf2nexus-2
  FIXTURES_SETUP nexus2cbf-2)

add_test(NAME nexus2cbf-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "i19-1.cbf"
    "i19-2.cbf")
set_tests_properties(nexus2cbf-cmp PROPERTIES
  FIXTURES_REQUIRED "nexus2cbf-1;nexus2cbf-2")

add_test(NAME h5dump-1
  COMMAND ${CMAKE_COMMAND}
    "-Dinput-file=i19-1.h5"
    "-Doutput-file=i19-1.dump"
    -P "${PROJECT_BINARY_DIR}/h5dump-$<CONFIG>.cmake")
set_tests_properties(h5dump-1 PROPERTIES
  FIXTURES_REQUIRED cbf2nexus-1
  FIXTURES_SETUP h5dump-1)

add_test(NAME h5dump-2
  COMMAND ${CMAKE_COMMAND}
    "-Dinput-file=i19-2.h5"
    "-Doutput-file=i19-2.dump"
    -P "${PROJECT_BINARY_DIR}/h5dump-$<CONFIG>.cmake")
set_tests_properties(h5dump-2 PROPERTIES
  FIXTURES_REQUIRED cbf2nexus-2
  FIXTURES_SETUP h5dump-2)

add_test(NAME h5dump-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "i19-1.dump"
    "i19-2.dump")
set_tests_properties(h5dump-cmp PROPERTIES
  FIXTURES_REQUIRED "h5dump-1;h5dump-2")

add_test(NAME cbf2nexus1-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "i19-1.h5")
set_tests_properties(cbf2nexus1-cleanup PROPERTIES
  FIXTURES_CLEANUP cbf2nexus-1)

add_test(NAME nexus2cbf1-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "i19-1.cbf")
set_tests_properties(nexus2cbf1-cleanup PROPERTIES
  FIXTURES_CLEANUP nexus2cbf-1)

add_test(NAME cbf2nexus2-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "i19-2.h5")
set_tests_properties(cbf2nexus2-cleanup PROPERTIES
  FIXTURES_CLEANUP cbf2nexus-2)

add_test(NAME nexus2cbf2-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "i19-2.cbf")
set_tests_properties(nexus2cbf2-cleanup PROPERTIES
  FIXTURES_CLEANUP nexus2cbf-2)

add_test(NAME h5dump1-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "i19-1.dump")
set_tests_properties(h5dump1-cleanup PROPERTIES
  FIXTURES_CLEANUP h5dump-1)

add_test(NAME h5dump2-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "i19-2.dump")
set_tests_properties(h5dump2-cleanup PROPERTIES
  FIXTURES_CLEANUP h5dump-2)


#
# reals
add_test(NAME reals-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${CBF_DATA_INPUT}/testrealin.cbf"
    "${CMAKE_CURRENT_BINARY_DIR}")
set_tests_properties(reals-setup PROPERTIES
  FIXTURES_SETUP reals-setup
  REQUIRED_FILES "${CBF_DATA_INPUT}/testrealin.cbf")

add_test(NAME reals
  COMMAND testreals)
set_tests_properties(reals PROPERTIES
  FIXTURES_REQUIRED reals-setup
  FIXTURES_SETUP reals)

add_test(NAME reals-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "testrealin.cbf"
    "testrealout.cbf")
set_tests_properties(reals-cmp PROPERTIES
  FIXTURES_REQUIRED reals)

add_test(NAME reals-setup-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testrealin.cbf")
set_tests_properties(reals-setup-cleanup PROPERTIES
  FIXTURES_CLEANUP reals-setup)

add_test(NAME reals-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testrealout.cbf")
set_tests_properties(reals-cleanup PROPERTIES
  FIXTURES_CLEANUP reals)


#
# flat
add_test(NAME flat-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${CBF_DATA_INPUT}/testflatin.cbf"
    "${CMAKE_CURRENT_BINARY_DIR}")
set_tests_properties(flat-setup PROPERTIES
  FIXTURES_SETUP flat-setup
  REQUIRED_FILES "${CBF_DATA_INPUT}/testflatin.cbf")

add_test(NAME flat
  COMMAND testflat)
set_tests_properties(flat PROPERTIES
  FIXTURES_REQUIRED flat-setup
  FIXTURES_SETUP flat)

add_test(NAME flat-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "testflatin.cbf"
    "testflatout.cbf")
set_tests_properties(flat-cmp PROPERTIES
  FIXTURES_REQUIRED flat)

add_test(NAME flat-setup-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testflatin.cbf")
set_tests_properties(flat-setup-cleanup PROPERTIES
  FIXTURES_CLEANUP flat-setup)

add_test(NAME flat-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testflatout.cbf")
set_tests_properties(flat-cleanup PROPERTIES
  FIXTURES_CLEANUP flat)


#
# flatpacked
add_test(NAME flatpacked-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${CBF_DATA_INPUT}/testflatpackedin.cbf"
    "${CMAKE_CURRENT_BINARY_DIR}")
set_tests_properties(flatpacked-setup PROPERTIES
  FIXTURES_SETUP flatpacked-setup
  REQUIRED_FILES "${CBF_DATA_INPUT}/testflatpackedin.cbf")

add_test(NAME flatpacked
  COMMAND testflatpacked)
set_tests_properties(flatpacked PROPERTIES
  FIXTURES_REQUIRED flatpacked-setup
  FIXTURES_SETUP flatpacked)

add_test(NAME flatpacked-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "testflatpackedin.cbf"
    "testflatpackedout.cbf")
set_tests_properties(flatpacked-cmp PROPERTIES
  FIXTURES_REQUIRED flatpacked)

add_test(NAME flatpacked-setup-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testflatpackedin.cbf")
set_tests_properties(flatpacked-setup-cleanup PROPERTIES
  FIXTURES_CLEANUP flatpacked-setup)

add_test(NAME flatpacked-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "testflatpackedout.cbf")
set_tests_properties(flatpacked-cleanup PROPERTIES
  FIXTURES_CLEANUP flatpacked)


if(CBF_ENABLE_FORTRAN)
  #
  # xds_binary-flat
  add_test(NAME xds_binary-flat
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:test_xds_binary>"
      "-Dinput=testflatin.cbf"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/test_xds_bin_testflatout.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CBF_DATA_INPUT}")
  set_tests_properties(xds_binary-flat PROPERTIES
    FIXTURES_SETUP xds_binary-flat
    REQUIRED_FILES "${CBF_DATA_INPUT}/testflatin.cbf")

  add_test(NAME xds_binary-flat-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/test_xds_bin_testflatout_orig.out"
      "test_xds_bin_testflatout.out")
  set_tests_properties(xds_binary-flat-cmp PROPERTIES
    FIXTURES_REQUIRED xds_binary-flat
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/test_xds_bin_testflatout_orig.out")

  add_test(NAME xds_binary-flat-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "test_xds_bin_testflatout.out")
  set_tests_properties(xds_binary-flat-cleanup PROPERTIES
    FIXTURES_CLEANUP xds_binary-flat)


  #
  # xds_binary-flatpacked
  add_test(NAME xds_binary-flatpacked
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:test_xds_binary>"
      "-Dinput=testflatpackedin.cbf"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/test_xds_bin_testflatpackedout.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CBF_DATA_INPUT}")
  set_tests_properties(xds_binary-flatpacked PROPERTIES
    FIXTURES_SETUP xds_binary-flatpacked
    REQUIRED_FILES "${CBF_DATA_INPUT}/testflatpackedin.cbf")

  add_test(NAME xds_binary-flatpacked-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/test_xds_bin_testflatpackedout_orig.out"
      "test_xds_bin_testflatpackedout.out")
  set_tests_properties(xds_binary-flatpacked-cmp PROPERTIES
    FIXTURES_REQUIRED xds_binary-flatpacked
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/test_xds_bin_testflatpackedout_orig.out")

  add_test(NAME xds_binary-flatpacked-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "test_xds_bin_testflatpackedout.out")
  set_tests_properties(xds_binary-flatpacked-cleanup PROPERTIES
    FIXTURES_CLEANUP xds_binary-flatpacked)


  #
  # fcb_read_image-flat
  add_test(NAME fcb_read_image-flat
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:test_fcb_read_image>"
      "-Dinput=testflatin.cbf"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/test_fcb_read_testflatout.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CBF_DATA_INPUT}")
  set_tests_properties(fcb_read_image-flat PROPERTIES
    FIXTURES_SETUP fcb_read_image-flat
    REQUIRED_FILES "${CBF_DATA_INPUT}/testflatin.cbf")

  add_test(NAME fcb_read_image-flat-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/test_fcb_read_testflatout_orig.out"
      "test_fcb_read_testflatout.out")
  set_tests_properties(fcb_read_image-flat-cmp PROPERTIES
    FIXTURES_REQUIRED fcb_read_image-flat
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/test_fcb_read_testflatout_orig.out")

  add_test(NAME fcb_read_image-flat-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "test_fcb_read_testflatout.out")
  set_tests_properties(fcb_read_image-flat-cleanup PROPERTIES
    FIXTURES_CLEANUP fcb_read_image-flat)


  #
  # fcb_read_image-flatpacked
  add_test(NAME fcb_read_image-flatpacked
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:test_fcb_read_image>"
      "-Dinput=testflatpackedin.cbf"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/test_fcb_read_testflatpackedout.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CBF_DATA_INPUT}")
  set_tests_properties(fcb_read_image-flatpacked PROPERTIES
    FIXTURES_SETUP fcb_read_image-flatpacked
    REQUIRED_FILES "${CBF_DATA_INPUT}/testflatpackedin.cbf")

  add_test(NAME fcb_read_image-flatpacked-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/test_fcb_read_testflatpackedout_orig.out"
      "test_fcb_read_testflatpackedout.out")
  set_tests_properties(fcb_read_image-flatpacked-cmp PROPERTIES
    FIXTURES_REQUIRED fcb_read_image-flatpacked
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/test_fcb_read_testflatpackedout_orig.out")

  add_test(NAME fcb_read_image-flatpacked-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "test_fcb_read_testflatpackedout.out")
  set_tests_properties(fcb_read_image-flatpacked-cleanup PROPERTIES
    FIXTURES_CLEANUP fcb_read_image-flatpacked)
endif()


#
# sauter_test
add_test(NAME sauter-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${CBF_DATA_OUTPUT}/adscconverted_flat_orig.cbf"
    "adscconverted_flat.cbf")
set_tests_properties(sauter-setup PROPERTIES
  FIXTURES_SETUP sauter-setup
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/adscconverted_flat_orig.cbf")

add_test(NAME sauter
  COMMAND sauter_test)
set_tests_properties(sauter PROPERTIES
  FIXTURES_REQUIRED sauter-setup
  FIXTURES_SETUP sauter)

add_test(NAME sauter-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "adscconverted_flat.cbf")
set_tests_properties(sauter-cleanup PROPERTIES
  FIXTURES_CLEANUP sauter)


#
# changtestcompression
add_test(NAME changtestcompression
  COMMAND changtestcompression)
set_tests_properties(changtestcompression PROPERTIES
  FIXTURES_SETUP changtestcompression)

add_test(NAME changtestcompression-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "CTC.cbf")
set_tests_properties(changtestcompression-cleanup PROPERTIES
  FIXTURES_CLEANUP changtestcompression)


#
# tiff2cbf-XRD1621
#
# 0.9.7 does not have "-c" option (as in "-cn") but 0.9.8 fails unless
# it is specified.
add_test(NAME tiff2cbf-XRD1621
  COMMAND tiff2cbf # -cn
    "${CBF_DATA_INPUT}/XRD1621.tif"
    "XRD1621.cbf")
set_tests_properties(tiff2cbf-XRD1621 PROPERTIES
  FIXTURES_SETUP tiff2cbf-XRD1621
  REQUIRED_FILES "${CBF_DATA_INPUT}/XRD1621.tif")

add_test(NAME tiff2cbf-XRD1621-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/XRD1621_orig.cbf"
    "XRD1621.cbf")
set_tests_properties(tiff2cbf-XRD1621-cmp PROPERTIES
  FIXTURES_REQUIRED tiff2cbf-XRD1621
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/XRD1621_orig.cbf")

add_test(NAME tiff2cbf-XRD1621-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "XRD1621.cbf")
set_tests_properties(tiff2cbf-XRD1621-cleanup PROPERTIES
  FIXTURES_CLEANUP tiff2cbf-XRD1621)


#
# cif2cbf-XRD1621
add_test(NAME cif2cbf-XRD1621
  COMMAND cif2cbf -I 4 -C 100. -L 0. -e n -c b
    -i "${CBF_DATA_OUTPUT}/XRD1621_orig.cbf"
    -o "XRD1621_I4encbC100.cbf")
set_tests_properties(cif2cbf-XRD1621 PROPERTIES
  FIXTURES_SETUP cif2cbf-XRD1621
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/XRD1621_orig.cbf")

add_test(NAME cif2cbf-XRD1621-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${CBF_DATA_OUTPUT}/XRD1621_I4encbC100_orig.cbf"
    "XRD1621_I4encbC100.cbf")
set_tests_properties(cif2cbf-XRD1621-cmp PROPERTIES
  FIXTURES_REQUIRED cif2cbf-XRD1621
  REQUIRED_FILES "${CBF_DATA_OUTPUT}/XRD1621_I4encbC100_orig.cbf")

add_test(NAME cif2cbf-XRD1621-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "XRD1621_I4encbC100.cbf")
set_tests_properties(cif2cbf-XRD1621-cleanup PROPERTIES
  FIXTURES_CLEANUP cif2cbf-XRD1621)


#
# java
if(CBF_ENABLE_JAVA)
  add_test(NAME java-setup-c
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:ctestcbf>"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/testcbfc.txt"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}")
  set_tests_properties(java-setup-c PROPERTIES
    FIXTURES_SETUP java-setup-c
    REQUIRED_FILES "${EXAMPLES}/template_pilatus6m_2463x2527.cbf")

  add_test(NAME java-setup-java
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=${Java_JAVA_EXECUTABLE};-Djava.library.path=${CMAKE_BINARY_DIR}/lib/;-cp;$<TARGET_PROPERTY:cbflib,JAR_FILE>:$<TARGET_PROPERTY:testcbf,JAR_FILE>;testcbf"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/testcbfj.txt"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}")
  set_tests_properties(java-setup-java PROPERTIES
    FIXTURES_SETUP java-setup-java
    REQUIRED_FILES "${EXAMPLES}/template_pilatus6m_2463x2527.cbf")

  add_test(NAME java-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "testcbfc.txt"
      "testcbfj.txt")
  set_tests_properties(java-cmp PROPERTIES
    REQUIRED_FIXTURES "java-setup-c;java-setup-java")

  add_test(NAME java-cleanup-c
    COMMAND ${CMAKE_COMMAND} -E rm "testcbfc.txt")
  set_tests_properties(java-cleanup-c PROPERTIES
    FIXTURES_CLEANUP java-setup-c)

  add_test(NAME java-cleanup-java
    COMMAND ${CMAKE_COMMAND} -E rm "testcbfj.txt")
  set_tests_properties(java-cleanup-java PROPERTIES
    FIXTURES_CLEANUP java-setup-java)
endif()


#
# dectris
add_test(NAME dectris-setup
  COMMAND ${CMAKE_COMMAND} -E copy
    "${TEMPLATES}/cbf_6M_template.cbf"
    "${CMAKE_CURRENT_BINARY_DIR}")
set_tests_properties(dectris-setup PROPERTIES
  REQUIRED_FILES "${TEMPLATES}/cbf_6M_template.cbf"
  FIXTURES_SETUP dectris-setup)

add_test(NAME dectris
  COMMAND cbf_template_t)
set_tests_properties(dectris PROPERTIES
  FIXTURES_REQUIRED dectris-setup
  FIXTURES_SETUP dectris)

add_test(NAME dectris-cmp
  COMMAND ${CMAKE_COMMAND} -E compare_files
    "${TEMPLATES}/cbf_test_orig.out"
    "cbf_template_t.out")
set_tests_properties(dectris-cmp PROPERTIES
  FIXTURES_REQUIRED dectris)

add_test(NAME dectris-setup-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "cbf_6M_template.cbf")
set_tests_properties(dectris-setup-cleanup PROPERTIES
  FIXTURES_CLEANUP dectris-setup)

add_test(NAME dectris-cleanup
  COMMAND ${CMAKE_COMMAND} -E rm "cbf_template_t.out")
set_tests_properties(dectris-cleanup PROPERTIES
  FIXTURES_CLEANUP dectris)


#
# Python
#
# Copy the test scripts to ${CMAKE_CURRENT_BINARY_DIR} to prevent
# `import pycbf` from importing
# ${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf.py rather than
# ${CMAKE_CURRENT_BINARY_DIR}/pycbf; this would not be necessary if
# pycbf.py were removed from ${CMAKE_CURRENT_SOURCE_DIR}/pycbf.
# Arbitrarily run the Python tests in
# ${CMAKE_CURRENT_BINARY_DIR}/pycbf because it is guaranteed to exist
# and the first tests look for their input files in the parent
# directory.
if(CBF_ENABLE_PYTHON)
  add_test(NAME pycbf-test1-setup
    COMMAND ${CMAKE_COMMAND} -E copy
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test1.py"
      "${CMAKE_CURRENT_BINARY_DIR}")
  set_tests_properties(pycbf-test1-setup PROPERTIES
    REQUIRED_FILES "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test1.py"
    FIXTURES_SETUP pycbf-test1-setup)

  add_test(NAME pycbf-test1
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:Python::Interpreter>;../pycbf_test1.py"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/pycbf_test1.raw"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/pycbf")
  set_tests_properties(pycbf-test1 PROPERTIES
    FIXTURES_REQUIRED "img2cif-flatpacked-cif;pycbf-test1-setup"
    FIXTURES_SETUP pycbf-test1)

  add_test(NAME pycbf-test1-standardize-numbers
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:cbf_standardize_numbers>;-;4"
      "-Dinput-file=pycbf_test1.raw"
      "-Doutput-file=pycbf_test1.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-test1-standardize-numbers PROPERTIES
    FIXTURES_REQUIRED pycbf-test1
    FIXTURES_SETUP pycbf-test1-standardize-numbers)

  add_test(NAME pycbf-test1-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/pycbf_test1_orig.out"
      "pycbf_test1.out")
  set_tests_properties(pycbf-test1-cmp PROPERTIES
    FIXTURES_REQUIRED pycbf-test1-standardize-numbers
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/pycbf_test1_orig.out")

  add_test(NAME pycbf-test1-setup-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test1.py")
  set_tests_properties(pycbf-test1-setup-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test1-setup)

  add_test(NAME pycbf-test1-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test1.raw")
  set_tests_properties(pycbf-test1-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test1)

  add_test(NAME pycbf-test1-standardize-numbers-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test1.out")
  set_tests_properties(pycbf-test1-standardize-numbers-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test1-standardize-numbers)


  add_test(NAME pycbf-test2-setup
    COMMAND ${CMAKE_COMMAND} -E copy
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test2.py"
      "${CMAKE_CURRENT_BINARY_DIR}")
  set_tests_properties(pycbf-test2-setup PROPERTIES
    REQUIRED_FILES "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test2.py"
    FIXTURES_SETUP pycbf-test2-setup)

  add_test(NAME pycbf-test2
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:Python::Interpreter>;../pycbf_test2.py"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/pycbf_test2.raw"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/pycbf")
  set_tests_properties(pycbf-test2 PROPERTIES
    FIXTURES_REQUIRED "convert_image-adscimg;pycbf-test2-setup"
    FIXTURES_SETUP pycbf-test2)

  add_test(NAME pycbf-test2-standardize-numbers
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:cbf_standardize_numbers>;-;4"
      "-Dinput-file=pycbf_test2.raw"
      "-Doutput-file=pycbf_test2.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-test2-standardize-numbers PROPERTIES
    FIXTURES_REQUIRED pycbf-test2
    FIXTURES_SETUP pycbf-test2-standardize-numbers)

  add_test(NAME pycbf-test2-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/pycbf_test2_orig.out"
      "pycbf_test2.out")
  set_tests_properties(pycbf-test2-cmp PROPERTIES
    FIXTURES_REQUIRED pycbf-test2-standardize-numbers
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/pycbf_test2_orig.out")

  add_test(NAME pycbf-test2-setup-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test2.py")
  set_tests_properties(pycbf-test2-setup-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test2-setup)

  add_test(NAME pycbf-test2-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test2.raw")
  set_tests_properties(pycbf-test2-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test2)

  add_test(NAME pycbf-test2-standardize-numbers-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test2.out")
  set_tests_properties(pycbf-test2-standardize-numbers-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test2-standardize-numbers)


  add_test(NAME pycbf-test3-setup
    COMMAND ${CMAKE_COMMAND} -E copy
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test3.py"
      "${CMAKE_CURRENT_BINARY_DIR}")
  set_tests_properties(pycbf-test3-setup PROPERTIES
    REQUIRED_FILES "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test3.py"
    FIXTURES_SETUP pycbf-test3-setup)

  add_test(NAME pycbf-test3
    COMMAND
      Python::Interpreter "pycbf_test3.py")

  add_test(NAME pycbf-test3-setup-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test3.py")
  set_tests_properties(pycbf-test3-setup-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test3-setup)


  add_test(NAME pycbf-test4-setup
    COMMAND ${CMAKE_COMMAND} -E copy
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test4.py"
      "${CMAKE_CURRENT_BINARY_DIR}")
  set_tests_properties(pycbf-test4-setup PROPERTIES
    REQUIRED_FILES "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_test4.py"
    FIXTURES_SETUP pycbf-test4-setup)

  add_test(NAME pycbf-test4
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:Python::Interpreter>;../pycbf_test4.py"
      "-Doutput-file=${CMAKE_CURRENT_BINARY_DIR}/pycbf_test4.raw"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake"
    WORKING_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/pycbf")
  set_tests_properties(pycbf-test4 PROPERTIES
    FIXTURES_REQUIRED "img2cif-flatpacked-cif;pycbf-test4-setup"
    FIXTURES_SETUP pycbf-test4)

  add_test(NAME pycbf-test4-standardize-numbers
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:cbf_standardize_numbers>;-;4"
      "-Dinput-file=pycbf_test4.raw"
      "-Doutput-file=pycbf_test4.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-test4-standardize-numbers PROPERTIES
    FIXTURES_REQUIRED pycbf-test4
    FIXTURES_SETUP pycbf-test4-standardize-numbers)

  add_test(NAME pycbf-test4-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/pycbf_test4_orig.out"
      "pycbf_test4.out")
  set_tests_properties(pycbf-test4-cmp PROPERTIES
    FIXTURES_REQUIRED pycbf-test4-standardize-numbers
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/pycbf_test4_orig.out")

  add_test(NAME pycbf-test4-setup-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test4.py")
  set_tests_properties(pycbf-test4-setup-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test4-setup)

  add_test(NAME pycbf-test4-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test4.raw" "pycbf/newtest1.cbf")
  set_tests_properties(pycbf-test4-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test4)

  add_test(NAME pycbf-test4-standardize-numbers-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_test4.out")
  set_tests_properties(pycbf-test4-standardize-numbers-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-test4-standardize-numbers)


  add_test(NAME pycbf-fel-setup
    COMMAND ${CMAKE_COMMAND} -E copy
      "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_testfelaxes.py"
      "${CMAKE_CURRENT_BINARY_DIR}")
  set_tests_properties(pycbf-fel-setup PROPERTIES
    REQUIRED_FILES "${CMAKE_CURRENT_SOURCE_DIR}/pycbf/pycbf_testfelaxes.py"
    FIXTURES_SETUP pycbf-fel-setup)

  add_test(NAME pycbf-fel-setup-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "pycbf_testfelaxes.py")
  set_tests_properties(pycbf-fel-setup-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel-setup)


  add_test(NAME pycbf-fel1
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:Python::Interpreter>;pycbf_testfelaxes.py;${CMAKE_CURRENT_SOURCE_DIR}/pycbf/fel_test1.cbf"
      "-Doutput-file=fel_test1.raw"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-fel1 PROPERTIES
    FIXTURES_REQUIRED pycbf-fel-setup
    FIXTURES_SETUP pycbf-fel1)

  add_test(NAME pycbf-fel1-standardize-numbers
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:cbf_standardize_numbers>;-;4"
      "-Dinput-file=fel_test1.raw"
      "-Doutput-file=fel_test1.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-fel1-standardize-numbers PROPERTIES
    FIXTURES_REQUIRED pycbf-fel1
    FIXTURES_SETUP pycbf-fel1-standardize-numbers)

  add_test(NAME pycbf-fel1-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/fel_test1_orig.out"
      "fel_test1.out")
  set_tests_properties(pycbf-fel1-cmp PROPERTIES
    FIXTURES_REQUIRED pycbf-fel1-standardize-numbers
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/fel_test1_orig.out")

  add_test(NAME pycbf-fel1-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "fel_test1.raw")
  set_tests_properties(pycbf-fel1-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel1)

  add_test(NAME pycbf-fel1-standardize-numbers-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "fel_test1.out")
  set_tests_properties(pycbf-fel1-standardize-numbers-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel1-standardize-numbers)


  add_test(NAME pycbf-fel2
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:Python::Interpreter>;pycbf_testfelaxes.py;${CMAKE_CURRENT_SOURCE_DIR}/pycbf/fel_test2.cbf"
      "-Doutput-file=fel_test2.raw"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-fel2 PROPERTIES
    FIXTURES_REQUIRED pycbf-fel-setup
    FIXTURES_SETUP pycbf-fel2)

  add_test(NAME pycbf-fel2-standardize-numbers
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:cbf_standardize_numbers>;-;4"
      "-Dinput-file=fel_test2.raw"
      "-Doutput-file=fel_test2.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-fel2-standardize-numbers PROPERTIES
    FIXTURES_REQUIRED pycbf-fel2
    FIXTURES_SETUP pycbf-fel2-standardize-numbers)

  add_test(NAME pycbf-fel2-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/fel_test2_orig.out"
      "fel_test2.out")
  set_tests_properties(pycbf-fel2-cmp PROPERTIES
    FIXTURES_REQUIRED pycbf-fel2-standardize-numbers
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/fel_test2_orig.out")

  add_test(NAME pycbf-fel2-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "fel_test2.raw")
  set_tests_properties(pycbf-fel2-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel2)

  add_test(NAME pycbf-fel2-standardize-numbers-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "fel_test2.out")
  set_tests_properties(pycbf-fel2-standardize-numbers-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel2-standardize-numbers)


  add_test(NAME pycbf-fel3
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:Python::Interpreter>;pycbf_testfelaxes.py;${CBF_DATA_INPUT}/hit-20140306005258847.cbf"
      "-Doutput-file=fel_test3.raw"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-fel3 PROPERTIES
    FIXTURES_REQUIRED pycbf-fel-setup
    FIXTURES_SETUP pycbf-fel3)

  add_test(NAME pycbf-fel3-standardize-numbers
    COMMAND ${CMAKE_COMMAND}
      "-Dcommand=$<TARGET_FILE:cbf_standardize_numbers>;-;4"
      "-Dinput-file=fel_test3.raw"
      "-Doutput-file=fel_test3.out"
      -P "${CMAKE_CURRENT_SOURCE_DIR}/redirect.cmake")
  set_tests_properties(pycbf-fel3-standardize-numbers PROPERTIES
    FIXTURES_REQUIRED pycbf-fel3
    FIXTURES_SETUP pycbf-fel3-standardize-numbers)

  add_test(NAME pycbf-fel3-cmp
    COMMAND ${CMAKE_COMMAND} -E compare_files
      "${CBF_DATA_OUTPUT}/fel_test3_orig.out"
      "fel_test3.out")
  set_tests_properties(pycbf-fel3-cmp PROPERTIES
    FIXTURES_REQUIRED pycbf-fel3-standardize-numbers
    REQUIRED_FILES "${CBF_DATA_OUTPUT}/fel_test3_orig.out")

  add_test(NAME pycbf-fel3-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "fel_test3.raw")
  set_tests_properties(pycbf-fel3-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel3)

  add_test(NAME pycbf-fel3-standardize-numbers-cleanup
    COMMAND ${CMAKE_COMMAND} -E rm "fel_test3.out")
  set_tests_properties(pycbf-fel3-standardize-numbers-cleanup PROPERTIES
    FIXTURES_CLEANUP pycbf-fel3-standardize-numbers)
endif()
