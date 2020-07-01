<html>
  <p align="center">
    <img src="https://github.com/rrrrhys/blackjack/blob/master/_/deck.png" alt=""    width="150"/>
  </p>
___
</html>

<br/>
<br/>

**DATA**
<br/>
tens of thousands of images of card hands, each card photographed from a physical deck.  OpenCV used to find contours of each card and extract it from photograph.  images augmented with PIL to simulate different lighting conditions (brightness, contrast, color).  background imagery from [Oxford University Describable Textures Dataset](https://www.robots.ox.ac.uk/~vgg/data/dtd/) (DTD) used to create random scenes of card pairs (416x416).  further augmentation with imgaug and Shapely (size, rotation).  annotations recorded for bounding boxes containing the convex hull of each corner suit of each card.
<br/>
<br/>

<html>
  <p align="center">
    <img src="https://github.com/rrrrhys/blackjack/blob/master/_/c12.jpg" alt="" width="300"/>
    <img src="https://github.com/rrrrhys/blackjack/blob/master/_/card_pair.jpg" alt="" width="300"/>
  </p>
</html>

*fig. 1*:  card photographed against contrasting background; *fig. 2*:  extracted cards augmented and randomly paired with DTD background
<br/>
<br/>

<html>
  <p align="center">
  <img src="https://github.com/rrrrhys/blackjack/blob/master/_/convex_hull.png" alt="" width="608"/></p>
</html>

*fig. 3*:  extracted card, corner-suit bounding box, convex hull; illustrates three consecutive brightness levels (of ten used) to simulate alternative lighting conditions
<br/>
<br/>

**MODEL**
<br/>
YOLOv3 used for detection speed.  card dataset trained on top of weights of [Common Objects in Context Dataset](https://cocodataset.org/#home)-trained model (COCO).  includes fine-tuning pass incorporating early-stopping.
<br/>
<br/>

<html>
  <p align="center">
  <img src="https://github.com/rrrrhys/blackjack/blob/master/_/yolov3.png" alt="" width="608"/>
  </p>
 </html>

*fig. 4*:  [speed / accuracy comparison chart for YOLOv3](https://pjreddie.com/darknet/yolo/)
<br/>
<br/>

**NOTES**
<br/>
replace PIL in detection module with a combination of mss/OpenCV to increase live FPS on macbook/iphone feed; train on additional image sizes, augmentations and epoch-cycle lengths to improve detection results; train on a representative hand dataset to improve recognition and filtering of hand movements during use.
<br/>
<br/>

<html>
  <p align="center">
    <img src="https://github.com/rrrrhys/blackjack/blob/master/_/detect_1.png" alt="" width="300"/>
    <img src="https://github.com/rrrrhys/blackjack/blob/master/_/detect_2.png" alt="" width="300"/>
  </p>
</html>

*fig. 5*:  image detection results (initial model)
<br/>
<br/>

**NEXT STEPS**
<br/>
program in best statistical practices for blackjack given cards detected to allow players to learn / train in real time.
<br/>
___
**CREDITS**
<br/>

notebook 001.01 + deck.py adapted and modified from: https://github.com/geaxgx/playing-card-detection

xml_to_csv.py adapted and modified from: https://github.com/datitran/raccoon_dataset

notebooks 002.01-003 + remaining modules adapted and modified from: https://github.com/qqwweee/keras-yolo3

header icon: https://twitter.com/win_icons/status/939691143134027776?s=20
