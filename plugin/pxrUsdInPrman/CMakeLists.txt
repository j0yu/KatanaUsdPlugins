set(PXR_PACKAGE pxrUsdInPrman)

set(vtKatana_LIBRARY "")
if (NOT ${KATANA_API_VERSION} VERSION_LESS "3.0.0")
    set(vtKatana_LIBRARY "vtKatana")
endif()

pxr_plugin(${PXR_PACKAGE}
    KATANA_PLUGIN
    LIBRARIES
        katanaPluginApi
        usdGeom
        usdKatana
        ${vtKatana_LIBRARY}
    
    PRIVATE_HEADERS
        declarePackageOps.h
    
    CPPFILES
        register.cpp
        prmanGeometryDecorator.cpp        
)
