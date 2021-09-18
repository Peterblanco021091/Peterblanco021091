- 👋 Hi, I’m @Peterblanco021091
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Peterblanco021091/Peterblanco021091 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
################################################ ############################
# Copyright (c) 2014-2019 desarrolladores de libbitcoin (ver COPIA).
#
# CÓDIGO FUENTE GENERADO, NO EDITAR EXCEPTO EXPERIMENTALMENTE
#
################################################ ############################
# FindBitcoin
#
# Use este módulo invocando find_package con el formulario ::
#
# find_package (Bitcoin
# [versión] # versión mínima
# [REQUERIDO] # Falla con error si no se encuentra libbitcoin
#)
#
# Define lo siguiente para su uso:
#
# bitcoin_FOUND: verdadero si se encuentran los encabezados y las bibliotecas solicitadas
# bitcoin_INCLUDE_DIRS - incluye directorios para bibliotecas bitcoin
# bitcoin_LIBRARY_DIRS - directorios de enlaces para bibliotecas bitcoin
# bitcoin_LIBRARIES - bibliotecas de bitcoin que se vincularán
# bitcoin_PKG: especificación del paquete bitcoin pkg-config.
#

si (MSVC)
    si (Bitcoin_FIND_REQUIRED)
        establecer (_bitcoin_MSG_STATUS "SEND_ERROR")
    demás ()
        establecer (_bitcoin_MSG_STATUS "ESTADO")
    terminara si()

    establecer (bitcoin_FOUND falso)
    mensaje ($ {_ bitcoin_MSG_STATUS} "Actualmente no se admite la detección del entorno MSVC para 'bitcoin'").
demás ()
    # requerido
    si (Bitcoin_FIND_REQUIRED)
        set (_bitcoin_REQUIRED "REQUIRED")
    terminara si()

    # tranquilo
    si (Bitcoin_FIND_QUIETLY)
        set (_bitcoin_QUIET "QUIET")
    terminara si()

    # modulepec
    si (Bitcoin_FIND_VERSION_COUNT EQUAL 0)
        conjunto (_bitcoin_MODULE_SPEC "libbitcoin")
    demás ()
        si (Bitcoin_FIND_VERSION_EXACT)
            conjunto (_bitcoin_MODULE_SPEC_OP "=")
        demás ()
            conjunto (_bitcoin_MODULE_SPEC_OP "> =")
        terminara si()

        establecer (_bitcoin_MODULE_SPEC "libbitcoin $ {_ bitcoin_MODULE_SPEC_OP} $ {Bitcoin_FIND_VERSION}")
    terminara si()

    pkg_check_modules (bitcoin $ {_ bitcoin_REQUIRED} $ {_ bitcoin_QUIET} "$ {_ bitcoin_MODULE_SPEC}")
    establecer (bitcoin_PKG "$ {_ bitcoin_MODULE_SPEC}")
terminara si()
