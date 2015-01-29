# georectifying_tools
georectifying tools

There is a need to sometimes georectify or re-georectify imagery strips when providing imagery services to the OpenStreetMap community. The provided imagery is in an area that is either covered by high-resolution Bing imagery or low-resolution imagery.

The provided imagery is already 'orthorectified'. However, the accuracy of the orthorectification varies and is not typically at the level desired.  

When high-resolution imagery is provided over an area in OpenStreetmap that has low-resolution imagery then typically there is no issue. The high-resolution imagery can be used to trace features

When high-resolution imagery is provided over an area in OpenStreetmap that has high-resolution imagery then there is a potential conflict, especially if there are already exisiting features. If nothing is done to fix the offset issues then mappers get confused. 

1. They might not know whether to move existing features to align with the newer imagery, or shit the newer imagery to align with the exisiting features.
2. A new mapper who navigates to the area on OpenStreetMap will likely be confused when if they see features misaligned with the shown imagery. These feature might have been traced off of newer imagery which is not in the default Bing layer. The mapper might not of thought to check the attribution or source of these features.

There is really no way to determine which image is more accurate without more data. The imagery from both Bing and the imagery we are pulling from come from the same imagery provider and is orthorectified according to their methods. 

fixes:

-Since the accuracy between the Bing imagery and the provided imagery can not be compared it would be preferable to georectify the provided imagery to the Bing imagery to reduce confusion of the mappers and not have to re-align exisiting features. ***We are looking for an easy, mostly automatic way to do this, preferably opensource.***

-The offset tool in JOSM could be use to shift the newer imagery to match the exisiting Bing imagery and features. However, this adds a little complexity as the mappers will need to edit using JOSM and the offset tool and download the offsets. Also, many times the offset is not a linear offset. 

-If a sufficient amount of relaiable GPS traces are collected in the field then the new image could be re-georectified using the GPS points. Then this new image would be the most accurate and could be used definitively for tracing. 
