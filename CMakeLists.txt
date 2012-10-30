# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Kapec, Peter Drahos
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( lrexlib-onigumura C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

add_definitions ( -DVERSION=\"${DIST_VERSION}\" )

find_package ( Oniguruma REQUIRED )
include_directories ( ${ONIGURUMA_INCLUDE_DIRS} )

install_lua_module ( rex_onig
  src/common.c
  src/oniguruma/lonig.c 
  src/oniguruma/lonig_f.c
  LINK ${ONIGURUMA_LIBRARIES} )
