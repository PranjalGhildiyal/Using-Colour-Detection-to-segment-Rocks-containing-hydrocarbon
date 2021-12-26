# Using-Colour-Detection-to-segment-Marcels-containing-hydrocarbon
Applying colour detection and masks to rock sections to detect the possible oil bearing formations, namely Vitrinite and liptinite.

Data consists of images of unlabeled rock sections.
The rock sections can be used to predict the possibility and the quantity of hydrocarbons present in the formation.
Only the rock types which have a characteristic high carbon content would be considered as possible hydrocarbon bering zones.

## Sample
>![1](https://github.com/PranjalGhildiyal/Using-Colour-Detection-to-segment-Rocks-containing-hydrocarbon/blob/main/Accessories/Sample.png)
>This is a section of rock from the Sayal Formation. Scale on top left corner.
>The data is unlabeled initially for any model to work on.
>We have total 6 such high resolution images (2560x1920) to work on.

## Mineral Content:
| Image no. | Vitrinite  | Liptinite | Inertinite |
| --------- | ---------- | --------- | ---------- |
| 1.  | 62.71  | 7.12 | 8.81 |
| 2.  | 67.31  | 8.89 | 7.30 |
| 3.  | 73.91  | 6.35 | 5.35 |
| 4.  | 26.22  | 12.00 | 7.11 |
| 5.  | 34.13  | 8.87 | 16.72 |
| 6.  | 42.65  | 10.29 | 6.25 |
>The above shows the composition of rock section indicating the quantity of various marcels present.
>Of these, Vitrinite and Liptinite are required to be segmented. Initially, we apply colour detection the the problem.

## Color Detection:
Colour Detection for Components in the given sample is applied.
>![Colour Detection](https://github.com/PranjalGhildiyal/Using-Colour-Detection-to-segment-Rocks-containing-hydrocarbon/blob/main/Accessories/Colour%20Detection.png)


## Color Extraction
The images were first converted to greyscale images.
>![Greyscale](https://github.com/PranjalGhildiyal/Using-Colour-Detection-to-segment-Rocks-containing-hydrocarbon/blob/main/Accessories/Greyscale.png)
### 1. Vitrinite
```diff
# We know that Vitrinite is grey(from the sample)
```
| Colour |Colour Name | Colour Code | Decimal Code (R,G,B) |
| ------ | ---------  | ----------- | -------------------- |
|![#f03c15](https://via.placeholder.com/15/A9A9A9/000000?text=+) | 		darkgray / darkgrey | #A9A9A9| rgb(169,169,169) |
|![#f03c15](https://via.placeholder.com/15/808080/000000?text=+) | 	gray / grey | #808080| rgb(128,128,128) |
|![#f03c15](https://via.placeholder.com/15/696969/000000?text=+) | 	dimgray / dimgrey | #696969 | rgb(105,105,105)|
|![#f03c15](https://via.placeholder.com/15/5E5D5D/000000?text=+) | Grey	| #5E5D5D | rgb(94,93,93) |
|![#f03c15](https://via.placeholder.com/15/3C3C3C/000000?text=+) | 	Grey | #3C3C3C | rgb(60,60,60) |
>These shades of grey are used to detect Vitrinite

#### Using mask to extract grey Vitrinite
>A mask was applied using [OpenCV](https://opencv.org/) to extract the grey portion of the image.
>![Mask](https://github.com/PranjalGhildiyal/Using-Colour-Detection-to-segment-Rocks-containing-hydrocarbon/blob/main/Accessories/Mask-%20Vitrinite.png)
>The grey portion shows vitrinite and thus, a possibility of hydrocarbon presence.

