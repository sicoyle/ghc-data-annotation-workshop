# Data annotation specifications

## Specifications to guide annotations for a person tracking project

The information below is meant to guide discussion and provide pointers and considerations that a professional annotation team would have for a person detection annotation project.

### General Comments

- Only visible parts of people should be annotated.
- Only a person's silhouette should be annotated.
- Don't include bags, purses, baby carriages, shopping carts, etc. into a bounding box.
- Individuals should have the same identity if he/she/it/they appear/disappear several times throughout a video.
- Don't annotate small or really blurry people.

### Annotation Format

`CVAT` supports multiple annotation formats that may be found [here](https://opencv.github.io/cvat/docs/manual/advanced/formats/).

- To be chosen by the annotator. One example is `CVAT` XML file schema/metadata.

More information on the XML annotation format specifically may be found [here](https://opencv.github.io/cvat/docs/manual/advanced/xml_format/).
The link describes the tags that are present in the XML, what they mean, 
and demonstrates an annotation example using annotation boxes, polygons, etc.

#### Person Tracking

The annotation file should contain the following information per frame
(from either manual or interpolated annotations):

| Annotation        | Annotation Type                             | Encoded by                                                                                                                                                                                                             |
|-------------------|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Person (location) | Rectangular bounding box (x1, y1, x2, y2)   | x1: horizontal coordinate of the top left corner <br> y1: vertical coordinate of the top left corner <br> x2: horizontal coordinate of the bottom right corner <br> y2: vertical coordinate of the bottom right corner |
| Identity          | Number                                      | Number indicating the person's identity (maintained over time). |
| Occlusion  | Number                                      | Value: <li> Person is not occluded (0) <li> Person is partially occluded (<= 50%) (1) <li> Person is heavily occluded (>50%) (2) |
