# Pool Counter

## Flow
- Data collection by capturing it from a Google Map
- Image processing to find contours (GaussianBlur, Canny, dilate, and threshold)
- Find rectangles from contours by filtering contours that have four coordinate points and an area between 1000 and 15000
- Apply NMS (Non-Maximum Suppression) to select an area if there is more than one area that has an IOU above 90%.
- Calculate the number of ponds based on the number of contours.
- Calculate the area of the pond by assuming that:
  - 1cm = 47 pxl
  - 1cm = 50m (base on google map)

## Bottleneck
- Difficult to get parameters that can perfectly describe the contours of the pond.
- There are several pools that are not detected due to inappropriate contours.

## Area Improvement
- Perform parameter analysis to find a nicer pond contour.
- Uses an object detection model to detect pools.
