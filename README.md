# Aive Technical Test
This repos host the scripts and results for the technical test for the position of senior data scientist at Aive.
Two methods were used, one using the Google Cloud Video Intelligence API and the other using YOLOv3.

## Methods
We tried two methods to detect the people within the video:

- Google Cloud Video Intelligence API, which requires a functionnal account and the API to be activated (this test was performed using the free trial)
- YoloV3 algorithm trained with the COCO dataset

## Content
The repos is organised as follows:

- Two notebooks contains the scripts using Video Intelligence or YoloV3
- The 'video' directory contains the video to be analysed (extracted from youtube for the duration of the test)
- The 'results' directory contains the two videos generated by the scripts
- The 'yolo' directory contains the necessary files to use YoloV3 and COCO, except the weight file which is too heavy for github

## Video compression
It was necessary to run ffmpeg to create lower sized videos.

`ffmpeg -i DIOR_test_result.mp4 -vcodec h264 -b:v 1000k -acodec mp3 DIOR_test_result_c.mp4`

## A little discussion
Though this will likely be discussed during the interview, a few observations can be made:

- YoloV3 was very demanding on an old computer, but gives a pretty accurate result (including many objects detected but not displayed on the output video)
- Video Intelligence was much faster but with less accuracy. This is a beta version still.

## References

- YoloV3 algorithm and the COCO dataset can be found at: https://pjreddie.com/darknet/yolo/ ( https://arxiv.org/pdf/1804.02767.pdf )
- We also worked with the code provided by Nandini Bansal at : https://github.com/nandinib1999/object-detection-yolo-opencv
