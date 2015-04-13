# Effect parameters

##  Common Parameters:


=========== =============== ==============================================================
Name        Default values  Possible values
=========== =============== ==============================================================
duration    5.0             float
=========== =============== ==============================================================
timeOffset   0.0             float
=========== =============== ==============================================================

## Diving

###  Type: "diving"

###  Parameters:

** No specific parameter. **

###  Children:

The number of authorized children is in [1, 100].

### Example:
  <effect type="diving" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Canyon_de_Chelly_Navajo.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Monument_Valley.jpg"/>
  </effect>
## Explode

###  Type: "explode"

###  Parameters:

=========== =============== ==============================================================
Name        Default values  Possible values
=========== =============== ==============================================================
adapter     kenburnsAdapter none,panoramicAdapter,zoomAdapter,fixedAdapter,kenburnsAdapter
=========== =============== ==============================================================

###  Children:

There must be exactly one child node.

### Example:

  <effect type="explode" adapter="kenburnsAdapter" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
  </effect>

## Flower

###  Type: "flower"

###  Parameters:


=========== =============== ==============================================================
Name        Default values  Possible values
=========== =============== ==============================================================
adapter     kenburnsAdapter none,panoramicAdapter,zoomAdapter,fixedAdapter,kenburnsAdapter
=========== =============== ==============================================================

###  Children:

There must be exactly one child node.


### Example:

  <effect type="flower" adapter="kenburnsAdapter" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
  </effect>

## Kenburns

###  Type: "kenburns"

###  Parameters:


=========== =============== ==============================================================
Name        Default values  Possible values
=========== =============== ==============================================================
depthEnable true            true,false
=========== =============== ==============================================================
direction   positive        positive,negative
=========== =============== ==============================================================
adapter     kenburnsAdapter none,panoramicAdapter,zoomAdapter,fixedAdapter,kenburnsAdapter
=========== =============== ==============================================================

###  Children:

There must be exactly one child node.

### Example:

  <effect type="kenburns" depthEnable="true" direction="positive" adapter="kenburnsAdapter" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
  </effect>

## None

###  Type: "none"

###  Parameters:


=========== =============== ==============================================================
Name        Default values  Possible values
=========== =============== ==============================================================
depthEnable true            true,false
=========== =============== ==============================================================


###  Children:

There must be exactly one child node.

### Example:

  <effect type="none" depthEnable="true" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
  </effect>

## Panel

###  Type: "panel"

###  Parameters:


========== =============== ==============================================================
Name       Default values  Possible values
========== =============== ==============================================================
adapter    kenburnsAdapter none,panoramicAdapter,zoomAdapter,fixedAdapter,kenburnsAdapter
========== =============== ==============================================================

###  Children:

There must be exactly one child node.

### Example:

  <effect type="panel" adapter="kenburnsAdapter" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
  </effect>

## Rectangles

###  Type: "rectangles"

###  Parameters:


========== =============== ==============================================================
Name       Default values  Possible values
========== =============== ==============================================================
filterType grow            grow
========== =============== ==============================================================


###  Children:

There must be exactly one child node.

### Example:

  <effect type="rectangles" filterType="grow" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
  </effect>

## Rotator

###  Type: "rotator"

###  Parameters:

** No specific parameter. **

###  Children:

The number of authorized children is in [1, 100].

### Example:

  <effect type="rotator" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Canyon_de_Chelly_Navajo.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Monument_Valley.jpg"/>
  </effect>

## Slice

###  Type: "slice"

###  Parameters:

======= =============== ==============================================================
Name    Default values  Possible values
======= =============== ==============================================================
adapter kenburnsAdapter none,panoramicAdapter,zoomAdapter,fixedAdapter,kenburnsAdapter
======= =============== ==============================================================


###  Children:

There must be exactly one child node.

### Example:

  <effect type="slice" adapter="kenburnsAdapter" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Monument_Valley.jpg"/>
  </effect>

## Sliding

###  Type: "sliding"

###  Parameters:

** No specific parameter. **

###  Children:

The number of authorized children is in [1, 100].

### Example:

  <effect type="sliding" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Canyon_de_Chelly_Navajo.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Monument_Valley.jpg"/>
  </effect>

## Square

###  Type: "square"

###  Parameters:

** No specific parameter. **

###  Children:

The number of authorized children is in [1, 100].

### Example:

  <effect type="square" duration="5.0" timeOffset="0.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Canyon_de_Chelly_Navajo.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Monument_Valley.jpg"/>
  </effect>
