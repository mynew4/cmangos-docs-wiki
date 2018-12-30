## Introduction

M2 or MDX files are used to store polygon models along with their animations and other information. The file format is plain binary - no chunks.
Information is mainly from <http://www.pxr.dk/wowdev/wiki/index.php?title=M2> as well as from PseuWoW source.

## A note on coordinates

Blizzard uses an left-handed (?) Z-up coordinate system for the models. When loading, coordinate conversions must be applied for other coordinate systems. This also must be done for all animation data.

## File Structure

M2 files start with a header block which contains an index of number-offset pairs for all other data blocks. All other blocks follow after that one. Blocks are not delimited, but seem to be aligned to 16 byte boundaries.

## Header

| Position | Length    |
| -------- | --------- |
| 0        | 324 bytes |


The file format is identified by the magic string "MD20". Pairs of uint32 are given for every data block. nXXX describes the number of elements (not necessarily bytes) in this block while ofsXXX gives the offset to the beginning of the block. If a block does not exists, n and ofs are 0.

    Offset   Type            Description
    --------------------------------------------------------------------
    0x000    char[4]         Magic Bytes => "MD20"
    0x004    uint32          Version (0x100 before Burning Crusade, 0x104 after BC)
    0x008    uint32          nName - model name length (including \0)
    0x00C    uint32          ofsName - model name offset
    0x010    uint32          GlobalModelFlags (0,1,3 seen)
    0x014    uint32          nGlobalSequences - number of global sequences
    0x018    uint32          ofsGlobalSequences - offset to global sequences
    0x01C    uint32          nAnimations - number of animation sequences
    0x020    uint32          ofsAnimations - offset to animation sequences
    0x024    uint32          nAnimationLookup
    0x028    uint32          ofsAnimationLookup
    0x02C    uint32          nD - always 201 or 203 depending on client version
    0x030    uint32          ofsD
    0x034    uint32          nBones - number of bones
    0x038    uint32          ofsBones - offset to bones
    0x03C    uint32          nSkelBoneLookup - skeletal bone lookup table
    0x040    uint32          ofsSkelBoneLookup
    0x044    uint32          nVertices - number of vertices
    0x048    uint32          ofsVertices - offset to vertices
    0x04C    uint32          nViews - number of views (LOD versions?) 4 for every model
    0x050    uint32          ofsViews - offset to views
    0x054    uint32          nColors - number of color definitions
    0x058    uint32          ofsColors - offset to color definitions
    0x05C    uint32          nTextures - number of textures
    0x060    uint32          ofsTextures - offset to texture definitions
    0x064    uint32          nTransparency - number of transparency definitions
    0x068    uint32          ofsTransparency - offset to transparency definitions
    0x06C    uint32          nI - always 0
    0x070    uint32          ofsI
    0x074    uint32          nTexAnims - number of texture animations
    0x078    uint32          ofsTexAnims - offset to texture animations
    0x07C    uint32          nTexReplace
    0x080    uint32          ofsTexReplace
    0x084    uint32          nRenderFlags - number of blending mode definitions
    0x088    uint32          ofsRenderFlags - offset to blending mode definitions
    0x08C    uint32          nBoneLookupTable - bone lookup table
    0x090    uint32          ofsBoneLookupTable
    0x094    uint32          nTexLookup - number of texture lookup table entries
    0x098    uint32          ofsTexLookup - offset to texture lookup table
    0x09C    uint32          nTexUnits - texture unit definitions?
    0x0A0    uint32          ofsTexUnits
    0x0A4    uint32          nTransLookup - number of transparency lookup table entries
    0x0A8    uint32          ofsTransLookup - offset to transparency lookup table
    0x0AC    uint32          nTexAnimLookup - number of texture animation lookup table entries
    0x0B0    uint32          ofsTexAnimLookup - offset to texture animation lookup table
    0x0B4    float[14]       float values ... ? (in range -1000...1000, mostly in -20...30)
    0x0EC    uint32          nBoundingTriangles
    0x0F0    uint32          ofsBoundingTriangles
    0x0F4    uint32          nBoundingVertices
    0x0F8    uint32          ofsBoundingVertices
    0x0FC    uint32          nBoundingNormals
    0x100    uint32          ofsBoundingNormals
    0x104    uint32          nAttachments
    0x108    uint32          ofsAttachments
    0x10C    uint32          nAttachLookup
    0x110    uint32          ofsAttachLookup
    0x114    uint32          nAttachments_2
    0x118    uint32          ofsAttachments_2
    0x11C    uint32          nLights - number of lights
    0x120    uint32          ofsLights - offset to lights
    0x124    uint32          nCameras - number of cameras
    0x128    uint32          ofsCameras - offset to cameras
    0x12C    uint32          nCameraLookup
    0x130    uint32          ofsCameraLookup
    0x134    uint32          nRibbonEmitters - number of ribbon emitters
    0x138    uint32          ofsRibbonEmitters - offset to ribbon emitters
    0x13C    uint32          nParticleEmitters - number of particle emitters
    0x140    uint32          ofsParticleEmitters - offset to particle emitters

## Vertices

| Position           | Element size |
| ------------------ | ------------ |
| header.ofsVertices | 48 bytes     |


Vertices are global for all submeshes and views.

    Offset   Type            Description
    --------------------------------------------------------------------
    0x00     float[3]        Position (X,Y,Z)
    0x0C     uint8[4]        Bone weights (0 to 255)
    0x10     uint8[4]        Bone indices (0 to nBones-1)
    0x14     float[3]        Normal vector (nX, nY, nZ)
    0x20     float[2]        Texture coordinates (U, V)
    0x28     float[2]        unknown, mostly 0.0f

## Views

| Position        | Element size |
| --------------- | ------------ |
| header.ofsViews | 44 bytes     |


It is not clear what Views are for. But there are always 4 of them.

    Offset   Type            Description
    --------------------------------------------------------------------
    0x00     uint32          nIndex - number of elements in the index list
    0x04     uint32          ofsIndex - offset to the index list
    0x08     uint32          nTriangle - number of elements in the triangle list (this is 3* the number of triangles to be drawn)
    0x0C     uint32          ofsTriangle - offset to the triangle list
    0x10     uint32          nProps - number of elements in the vertex property list
    0x14     uint32          ofsProps - offset to the vertex property list
    0x18     uint32          nSubmesh - number of elements in the submesh list
    0x1C     uint32          ofsSubmesh - offset to the submesh list
    0x20     uint32          nTexture - number of elements in the texture list
    0x24     uint32          ofsTexture - offset to the texture list
    0x28     uint32          LOD distance or something?

### Indices

nIndex uint16 values - referencing vertices from the global Vertex list.

### Triangles

3 uint16 values per triangle - referencing the Index list

### Properties

4 bytes per Vertex. Those are indices into the BoneLookupTable for each Vertex.

### Submeshes

32 bytes per Submesh definition.

    Offset   Type            Description
    --------------------------------------------------------------------
    0x00     uint32          Mesh part ID
    0x04     uint16          ofsVertex - Starting vertex number, offset into the Vertex array
    0x06     uint16          nVertex - Number of vertices
    0x08     uint16          ofsTriangle - Starting triangle index
    0x0A     uint16          nTriangle - Number of triangle indices
    0x0C     uint16          nBoneLookup - Number of elements in the bone lookup table
    0x0E     uint16          ofsBoneLookup - Starting index in the bone lookup table
    0x10     uint16          unknown
    0x12     uint16          unsure - maybe root bone?
    0x14     float[3]        Vector (3d) - mass center?

**Mesh part ID**

These IDs are referenced for Geosets and such. For character models, each hairstyle/thick armor/etc is present in the mesh, so to render a character with a specific set of looks, some of the submeshes should be omitted based on this ID.The submeshes are sorted into groups. Groups are like this for character models. They can be different for other models.

    00**: Hairstyles
    01**: Facial1
    02**: Facial2
    03**: Facial3
    04**: Braces
    05**: Boots
    06**: Unknown
    07**: Ears
    08**: Wristbands
    09**: Kneepads?
    10**:
    11**: Related to pants
    12**: Tabard
    13**: Trousers / kilts
    14**:
    15**: Cape
    16**:
    17**: Eyeglows (including the deathknight ones)
    18**: Belt / bellypack

These are referenced in CreatureDisplayInfo.dbc->creatureGeosetData.
