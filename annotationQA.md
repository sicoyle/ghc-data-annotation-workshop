# Common data annotation Q&A

## Questions specific to person detection data annotations

1. How big do people have to be to require annotating?

All people and faces should be annotated.
However, `ignore regions` may be defined for regions of the image where people are too small.
`Ignore regions/zones` are common to have depending on your footage use case.

#### TODO(@Sam): bring in picture here

2. How precise should annotations be?

Annotations may be made with very tight bounding boxes, 
with 1-5% margin, 
or with >5% margin of boundaries.

#### TODO(@Sam): bring in picture here for each bounding box representation

4. How do you annotate faces?

Faces are annotated using a box from hairline down to the chin.
Ears are `not` incorporated into the box.

#### TODO(@Sam): bring in picture here

5. What is the `Identity` attribute?


| Annotation       | Annotation Type                             | Encoded by                                                                                                                                                                                                             |
|------------------|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Identity         | Number                                      | Number indicating the person's identify (maintained over time). |

`Identity` is not personally identifiable information in the way one might initially think.
It does **not** mean name, DOB, address, etc.
`Identity` in this sense means a means of which you can track the same person across different frames.
#### TODO(@Sam): bring in more details here referring to picture I bring in

#### TODO(@Sam): bring in picture here