set(ENGINE_SOURCES 
    main.cpp
    hello.c)

set(ENGINGE_HEADERS )

# Inclui diretórios para o compilador
include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/..
    ${CMAKE_CURRENT_SOURCE_DIR}/../include
)

# Cria o executável
add_executable(My2DEngine ${ENGINE_SOURCES} ${ENGINE_HEADERS})

if(TARGET SDL2)
    target_link_libraries(My2DEngine SDL2)
    
    # 🔥 INCLUI OS HEADERS DO SDL2
    target_include_directories(My2DEngine PRIVATE 
        ${CMAKE_SOURCE_DIR}/external/sdl2/include
    )
endif()

if(TARGET SDL2_image)
    target_link_libraries(My2DEngine SDL2_image)
endif()

# Configurações do target
target_compile_features(My2DEngine PRIVATE cxx_std_17)

# 🔥 CONFIGURAÇÕES ESPECÍFICAS PARA PLATAFORMA
if(WIN32)
    # No Windows, precisa linkar com essas bibliotecas
    target_link_libraries(My2DEngine 
        mingw32
        imm32
        version
        winmm
        setupapi
        advapi32
    )
endif()

message(STATUS "✅ Executável My2DEngine configurado com SDL2 embutido!")