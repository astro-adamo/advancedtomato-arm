# Copyright (c) 2006, 2007 MySQL AB
# 
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; version 2 of the License.
# 
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
# 
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA  02110-1301  USA

# About "mysqlclient_notls", see note in "client/CMakeLists.txt"

SET(CMAKE_C_FLAGS_DEBUG "${CMAKE_C_FLAGS_DEBUG} -DSAFEMALLOC -DSAFE_MUTEX")
ADD_DEFINITIONS("-DMYSQL_CLIENT")

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR}/include)

ADD_EXECUTABLE(mysql_client_test mysql_client_test.c ../mysys/my_memmem.c)
TARGET_LINK_LIBRARIES(mysql_client_test mysqlclient_notls wsock32)

ADD_EXECUTABLE(bug25714 bug25714.c)
TARGET_LINK_LIBRARIES(bug25714 mysqlclient_notls wsock32)
