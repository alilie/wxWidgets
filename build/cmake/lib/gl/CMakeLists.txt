#############################################################################
# Name:        build/cmake/lib/gl/CMakeLists.txt
# Purpose:     CMake file for gl library
# Author:      Tobias Taschner
# Created:     2016-10-03
# Copyright:   (c) 2016 wxWidgets development team
# Licence:     wxWindows licence
#############################################################################

wx_append_sources(GL_FILES OPENGL_CMN)

if(WXMSW)
    wx_append_sources(GL_FILES OPENGL_MSW)
elseif(WXGTK)
    wx_append_sources(GL_FILES OPENGL_GTK)
elseif(WXOSX_COCOA)
    wx_append_sources(GL_FILES OPENGL_OSX_COCOA)
elseif(WXOSX_IPHONE)
    wx_append_sources(GL_FILES OPENGL_OSX_IPHONE)
elseif(WXQT)
    wx_append_sources(GL_FILES OPENGL_QT)
elseif(WXX11)
    wx_append_sources(GL_FILES OPENGL_X11)
endif()

wx_add_library(wxgl ${GL_FILES})
wx_lib_include_directories(wxgl ${OPENGL_INCLUDE_DIR})
wx_lib_link_libraries(wxgl PUBLIC ${OPENGL_LIBRARIES})
