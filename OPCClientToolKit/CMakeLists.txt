cmake_minimum_required(VERSION 3.1)

# === PROJECT ==============================================================
include(cmakeTargets)
project(opcClientToolKit CXX)

# === CONFIG ===============================================================
set(PublicHeaderSubDirName libfins)

set(PublicHeaderLocation       "${CMAKE_CURRENT_SOURCE_DIR}")
set(HeaderLocation             "${CMAKE_CURRENT_SOURCE_DIR}")
set(SourceLocation             "${CMAKE_CURRENT_SOURCE_DIR}")


# === DEPS =================================================================
set(PublicHeaders
    ${PublicHeaderLocation}/OPCClient.h
    ${PublicHeaderLocation}/OPCClientToolKitDLL.h
    ${PublicHeaderLocation}/opccomn.h
    ${PublicHeaderLocation}/opcda.h
    ${PublicHeaderLocation}/OpcEnum.h
    ${PublicHeaderLocation}/OPCGroup.h
    ${PublicHeaderLocation}/OPCHost.h
    ${PublicHeaderLocation}/OPCItem.h
    ${PublicHeaderLocation}/OPCItemData.h
    ${PublicHeaderLocation}/OPCProperties.h
    ${PublicHeaderLocation}/OPCServer.h
    ${PublicHeaderLocation}/stdafx.h
    ${PublicHeaderLocation}/Transaction.h
)

set(Headers

)

set(Sources
    ${SourceLocation}/OPCClient.cpp
    ${SourceLocation}/opccomn_i.c
    ${SourceLocation}/opcda_i.c
    ${SourceLocation}/OpcEnum_i.c
    ${SourceLocation}/OPCGroup.cpp
    ${SourceLocation}/OPCHost.cpp
    ${SourceLocation}/OPCItem.cpp
    ${SourceLocation}/OPCItemData.cpp
    ${SourceLocation}/OPCProperties.cpp
    ${SourceLocation}/OPCServer.cpp
    ${SourceLocation}/stdafx.cpp
    ${SourceLocation}/Transaction.cpp
)


set(LinkLibraries

)


set(FindPackages

)

set(OtherFiles

)

find_package(Qt5 COMPONENTS Core REQUIRED)
AddLibraryTarget(
    TargetName              ${PROJECT_NAME}

    PublicIncludeLocation   ${PublicHeaderLocation}
    IncludeLocation         ${HeaderLocation}
    SourceLocation          ${SourceLocation}

    LibMode                 STATIC

    PublicHeaders           ${PublicHeaders}
    Headers                 ${Headers}
    Sources                 ${Sources}

    LinkLibraries           ${LinkLibraries}
    FindPackages            ${FindPackages}

    OtherFiles              ${OtherFiles}

    #options
    RemoveLibPrefix
    GenerateBuildInfo
)
