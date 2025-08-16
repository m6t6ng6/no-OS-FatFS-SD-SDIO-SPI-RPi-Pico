cmake_minimum_required(VERSION 3.5)

project(simple_example C CXX ASM)

# linea para libreria
add_library(simple_example STATIC
    ../../src/ff15/source/ff.c
    ../../src/ff15/source/ffunicode.c
    #../../src/ff15/source/diskio.c
    ../../src/ff15/source/ffsystem.c
    #../../src/ff15/documents/res/app6.c
    #../../src/ff15/documents/res/app2.c
    #../../src/ff15/documents/res/app5.c
    #../../src/ff15/documents/res/app1.c
    #../../src/ff15/documents/res/app4.c
    #../../src/ff15/documents/res/app3.c
    ../../src/sd_driver/sd_card.c
    ../../src/sd_driver/sd_timeouts.c
    ../../src/sd_driver/SPI/sd_spi.c
    ../../src/sd_driver/SPI/my_spi.c
    ../../src/sd_driver/SPI/sd_card_spi.c
    ../../src/sd_driver/SDIO/sd_card_sdio.c
    ../../src/sd_driver/SDIO/rp2040_sdio.c
    ../../src/sd_driver/dma_interrupts.c
    ../../src/src/ff_stdio.c
    ../../src/src/util.c
    ../../src/src/crash.c
    ../../src/src/my_rtc.c
    ../../src/src/my_debug.c
    ../../src/src/file_stream.c
    ../../src/src/crc.c
    ../../src/src/f_util.c
    ../../src/src/glue.c
)

target_link_libraries(simple_example 
    pico_stdlib
    #no-OS-FatFS-SD-SDIO-SPI-RPi-Pico
    hardware_pio
    hardware_dma
    hardware_spi
    cmsis_core
    pico_aon_timer
)

target_include_directories(simple_example PUBLIC
    ../../include/FsLib/
    ../../include/
    ../../include/iostream/
    ../../src/include/
    ../../src/ff15/source/
    ../../src/sd_driver/
    ../../src/sd_driver/SDIO/
    ../../src/sd_driver/SPI/
)