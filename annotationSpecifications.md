# Data annotation specifications

## Specifications to guide annotations for a person detection project

The information below is meant to guide discussion and provide pointers and considerations that a professional annotation team would have for a person detection annotation project.

### General Comments

- Only visible parts of people should be annotated.
- Only a person's silhouette should be annotated.
- Don't include bags, purses, baby carriages, shopping carts, etc. into a bounding box.
- Individuals should have the same identity if he/she/it/they appear/disappear several times throughout a video.
- Don't annotate small or really blurry people.

### Downsampling

In Machine Learning, downsampling is when you reduce a dataset to a more manageable size.
Downsampling an image in particular is where you reduce the number of pixels to create a smaller file size.
This is helpful when dealing with resource constraints when using large amounts of input data. 

- Original videos may be 4k at 60 Hz.
- Videos should be downsampled to 1080p at 30Hz.
- Annotations for every frame are required.
Although, interpolation is allowed (ex: annotate every 10 frames and interpolate the rest).

### Annotation Format

`CVAT` supports multiple annotation formats that may be found [here](https://openvinotoolkit.github.io/cvat/docs/manual/advanced/formats/).

- To be chosen by the annotator. One example is `CVAT` XML file schema/metadata.

#### Person Detection

The annotation file should contain the following information per frame
(from either manual or interpolated annotations):

| Annotation       | Annotation Type                             | Encoded by                                                                                                                                                                                                             |
|------------------|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Person location  | Rectangular bounding box (x1, y1, x2, y2)   | x1: horizontal coordinate of the top left corner <br> y1: vertical coordinate of the top left corner <br> x2: horizontal coordinate of the bottom right corner <br> y2: vertical coordinate of the bottom right corner |
| Face location    | Rectangular bounding box (x1, y1, x2, y2)   | x1: horizontal coordinate of the top left corner <br> y1: vertical coordinate of the top left corner <br> x2: horizontal coordinate of the bottom right corner <br> y2: vertical coordinate of the bottom right corner |
| Identity         | Number                                      | Number indicating the person's identify (maintained over time). |
| Person Occlusion | Number                                      | Value: <li> Person is not occluded (0) <li> Person is partially occluded (<= 50%) (1) <li> Person is heavily occluded (>50%) (2) |
