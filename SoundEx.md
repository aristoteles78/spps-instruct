SoundEx functions
====================
SoundEx is a method used to find strings when the sound is known but the precise spelling isn't known.

Developed in 1918, the method searches out words with similar sounds based on phonetic assumptions about how certain letters are pronounced. SoundEx can be used to search names in a database (for example, where spellings and pronunciations for similar names may vary). The basic SoundEx algorithm is documented in a number of sources and, despite known limitations (for example, leading letter combinations such as ph and f won't match even though they sound the same), is supported in some form by most databases.
## Table 1. CLEM soundex functions
| Function                   | Result  | Description                                                                                                                                               |
|----------------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| soundex(STRING)            | Integer  | Returns the four-character SoundEx code for the specified STRING.                                                                                                          |
| soundex_difference(STRING1, STRING2)               | Integer  | Returns an integer between 0 and 4 that indicates the number of characters that are the same in the SoundEx encoding for the two strings, where 0 indicates no similarity and 4 indicates strong similarity or identical strings.                                                                                                 |

