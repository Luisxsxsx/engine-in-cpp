message("Configurando dependencias externas...")

FetchContent_Declare(
    sdl2
    URL https://github.com/libsdl-org/SDL/releases/download/release-3.2.26/SDL3-3.2.26.zip
    URL_HASH SHA256=739356eef1192fff9d641c320a8f5ef4a10506b8927def4b9ceb764c7e947369
)

FetchContent_Declare(
    sdl2_image
    URL https://github.com/libsdl-org/SDL_image/releases/download/release-3.2.4/SDL3_image-3.2.4.zip
)

FetchContent_MakeAvailable(sdl2 sdl2_image)

message(STATUS "✅ Dependências externas configuradas!")