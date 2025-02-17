cmake_minimum_required(VERSION 3.10)


set(OPENV2G_DIR ${CMAKE_CURRENT_SOURCE_DIR})

set(openv2g_SRCS
  ${OPENV2G_DIR}/src/appHandshake/appHandEXIDatatypes.c
  ${OPENV2G_DIR}/src/appHandshake/appHandEXIDatatypesDecoder.c
  ${OPENV2G_DIR}/src/appHandshake/appHandEXIDatatypesEncoder.c
  ${OPENV2G_DIR}/src/codec/BitInputStream.c
  ${OPENV2G_DIR}/src/codec/BitOutputStream.c
  ${OPENV2G_DIR}/src/codec/ByteStream.c
  ${OPENV2G_DIR}/src/codec/DecoderChannel.c
  ${OPENV2G_DIR}/src/codec/EncoderChannel.c
  ${OPENV2G_DIR}/src/codec/EXIHeaderDecoder.c
  ${OPENV2G_DIR}/src/codec/EXIHeaderEncoder.c
  ${OPENV2G_DIR}/src/codec/MethodsBag.c
  ${OPENV2G_DIR}/src/din/dinEXIDatatypes.c
  ${OPENV2G_DIR}/src/din/dinEXIDatatypesDecoder.c
  ${OPENV2G_DIR}/src/din/dinEXIDatatypesEncoder.c
  ${OPENV2G_DIR}/src/iso1/iso1EXIDatatypes.c
  ${OPENV2G_DIR}/src/iso1/iso1EXIDatatypesDecoder.c
  ${OPENV2G_DIR}/src/iso1/iso1EXIDatatypesEncoder.c
  ${OPENV2G_DIR}/src/iso2/iso2EXIDatatypes.c
  ${OPENV2G_DIR}/src/iso2/iso2EXIDatatypesDecoder.c
  ${OPENV2G_DIR}/src/iso2/iso2EXIDatatypesEncoder.c
  ${OPENV2G_DIR}/src/transport/v2gtp.c
  ${OPENV2G_DIR}/src/xmldsig/xmldsigEXIDatatypes.c
  ${OPENV2G_DIR}/src/xmldsig/xmldsigEXIDatatypesDecoder.c
  ${OPENV2G_DIR}/src/xmldsig/xmldsigEXIDatatypesEncoder.c
)

add_library(openv2g EXCLUDE_FROM_ALL ${openv2g_SRCS})

target_compile_options(openv2g PUBLIC
  ${ARCH_C_FLAGS}
)

target_include_directories(openv2g PUBLIC 
  ${OPENV2G_DIR}/src/appHandshake
  ${OPENV2G_DIR}/src/codec
  ${OPENV2G_DIR}/src/din
  ${OPENV2G_DIR}/src/iso1
  ${OPENV2G_DIR}/src/iso2
  ${OPENV2G_DIR}/src/transport
  ${OPENV2G_DIR}/src/xmldsig
)

