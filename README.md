# Game Boy Cartridge Circuit Boards

This is a repository listing all of my Game Boy game circuit board variants.

## Game Boy Board Links

| **Board Name**       | **Board Number**   | **Max ROM Size**       | **Max RAM Size**  | **Multicart Support?** | **Memory Family Used**          |
|----------------------|--------------------|------------------------|-------------------|------------------------|---------------------------------|
| MBC1 (Type B)        | GB-4DV4S-01B       | 4 MB                   | 32 KB             | No                     | Type B (29F016, 29F032, 29F033) |
| MBC3 (Type B)        | GB-4KV4S-01B       | 4 MB                   | 32 KB             | No                     | Type B (29F016, 29F032, 29F033) |
| MBC5 (Type B)        | GB-4AV8S-01B       | 4 MB                   | 128 KB            | No                     | Type B (29F016, 29F032, 29F033) |
| MBC3 Multicart       | GB-4KV8S-01B       | 4 MB (2x 2 MB, 4x 1MB) | 128 KB (4x 32 KB) | Yes                    | Type B (29F032, 29F033)         |
| MBC5 Multicart       | GB-4AV8S-01B       | 4 MB (2x 2 MB, 4x 1MB) | 128 KB (4x 32 KB) | Yes                    | Type B (29F032, 29F033)         |
| MBC1 (Type A)        | GB-2DV4S-01B       | 2 MB                   | 32 KB             | No                     | Type A (M29F160)                |
| MBC3 (Type A)        | GB-2KV4S-01B       | 2 MB                   | 32 KB             | No                     | Type A (M29F160)                |
| MBC5 (Type A)        | GB-2AV8S-01B       | 2 MB                   | 128 KB            | No                     | Type A (M29F160)                |
| MBC1 (Type A, FRAM)  | GB-2DF4S-01B       | 2 MB                   | 32 KB             | No                     | Type A (M29F160)                |
| MBC3 (Type A, FRAM)  | GB-2KF4S-01B       | 2 MB                   | 32 KB             | No                     | Type A (M29F160)                |
| MBC5 (Type A, FRAM)  | GB-2AF4S-01B       | 2 MB                   | 32 KB             | No                     | Type A (M29F160)                |

## Naming Convention

| GB       | \- | 2                 | A               | V              | 4            | S                                            | \- | 01       | A                                       |
| -------- | -- | ----------------- | --------------- | -------------- | ------------ | -------------------------------------------- | -- | -------- | --------------------------------------- |
| Game Boy |    | Max ROM Size (MB) | Mapper Chip     | SRAM or FRAM?  | Max RAM Size | Multicart Support                            |    | Revision | Memory Family                           |
|          |    | 1                 | N = None        | X = None       | 0 = None     | S = Single game                              |    |          | A = New EEPROM (M29F160)                |
|          |    | 2                 | D = MBC1        | V = SRAM       | 1 = 2 KB     | D = Multicart (2x, split max ROM/RAM space)  |    |          | B = NOS EEPROM (29F016, 29F032, 29F033) |
|          |    | 4                 | K = MBC3        | F = FRAM       | 2 = 8 KB     | Q = Multicart (4x, split max ROM/RAM space)  |    |          |                                         |
|          |    | 6                 | A = MBC5        |                | 4 = 32 KB    |                                              |    |          |                                         |
|          |    | 8                 |                 |                | 8 = 128 KB   |                                              |    |          |                                         |
