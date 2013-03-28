## Introduction

[[WDT Files]], [[ADT Files]], [[WMO Files]] and [[WDL Files]] follow a chunked structure, consisting of chunks of the following format:

    Offset   Type            Description
    ----------------------------------------------------------------------
    00h      char[4]         Chunk identifier - in reverse character order
    04h      uint32          Chunk size
    08h      size*bytes      Chunk data

The initial chunk in all of these files is an MVER chunk, specifying the version of the files in a 32-bit integer.
All files use little-endian byte order.