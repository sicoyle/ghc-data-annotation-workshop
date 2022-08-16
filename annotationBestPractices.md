# Data Annotation Best Practices

1. How big do people have to be to require annotating?

All people and faces should be annotated.
However, `ignore regions` may be defined for regions of the image where people are too small.
`Ignore regions/zones` are common to have depending on your footage use case.

For example, in the image below, the red region can be described as our `ignore region`.
This region will be excluded from annotations.
In the case that ships pass by in the water with passengers on deck, 
then we do not want them counted towards our data annotations.

![Ignore Region](./assets/ignoreRegion.jpg)

2. How precise should annotations be?

Annotations may be made with very tight bounding boxes, 
with 1-5% margin, 
or with >5% margin of boundaries.

Option 1: Below is a very tight bounding box with little to no margin of error:
![Tight Bounding Box](./assets/tightBoundingBox.jpg)

Option 2: Below is a looser bounding box with a 1-5% margin of error:
![Looser Bounding Box](./assets/looserBoundingBox.jpg)

Option 3: Below is the loosest bounding box with a >5% margin of error:
![Loosest Bounding Box](./assets/loosestBoundingBox.jpg)

For the purposes of this workshop, Option 2 is suitable for our use case.
Please utilize Option 2 for reference when performing your data annotations.

5. What is the `Identity` attribute?

| Annotation       | Annotation Type                             | Encoded by                                                                                                                                                                                                             |
|------------------|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Identity         | Number                                      | Number indicating the person's identify (maintained over time). |

`Identity` is not personally identifiable information in the way one might initially think.
It does **not** mean name, DOB, address, etc.
`Identity` in this sense refers to a means to track the same person across different frames.

`CVAT` creates automatic `IDs` which cannot be changed.
For example, the image below has the automatic `ID` of `PERSON 3`.
However, we refer to the person with the `Identity` label of `1`.
This is the `Identity` with which we will refer to this person throughout the duration of the video.
For these purposes, you may disregard the automatic `IDs` given to each of your annotations.
In other words, please disregard the numbers by the red `X` in the image.

![Identities](./assets/identity.jpg)