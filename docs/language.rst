.. _stupeflix_xml_langage:

Stupeflix XML Language
======================

To describe a movie, we will start by defining atoms, that creates a video stream or an audio stream, and operators to compose these elements. Operators transform one or several video/audio streams into one stream which can be further combined with other streams.

Atoms
-----

Atoms are responsible for generating a single video / audio stream directly from assets. They define a stream of audio or video (or both) with a fixed duration. They will be combined on the fly by the video generator.

Available atoms are:

``effect``

  Can be used to turn one or several images or video assets (image and video tags) into a video stream (with optional audio stream).

``text``

  Turn a text into a video stream, using some kind of text rendering effect.

``audio``

  Turn an audio asset into an audio stream.

``overlay``

  Add an overlay on top of an existing scene.

.. note::

  Image and video tags are not directly atoms, as the effect is responsible to handle aspect ratio adaptation if the input image or video aspect ratio is different from the generated video.

Operators
---------

An operator combines several audio/video streams into a single one.

Available operators are:

``sequence``

  This operator takes a set of streams and just concatenate them in time. The related tag is sequence, or body : top level tag is a sequence.

``stack``

  This operator takes a set of streams and display them together. The display order is the xml order : first in the list, first to be drawn, and so may be partially hidden by subsequent draws.

.. note::

  A stack or a sequence or effect can contain atoms, sequences, and stacks.

Effects
-------

You will find a complete descriptions of parameters for each kind of effects in :doc:`effects`.

A typical effect tag looks like:

.. code-block:: xml

  <effect type="diving"  duration="5.0" >
    <image filename="http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Canyon_de_Chelly_Navajo.jpg"/>
    <image filename="http://assets.stupeflix.com/code/images/Monument_Valley.jpg"/>
  </effect>

Transitions
-----------

A transition tag can only be inserted in a sequence tag (or in the body tag). It uses the previous and the next video sequences provided, overlap them (reducing the sequence total duration), and so generate a new video stream. Previous and next video sequences can be any video stream: effect or stack of complex effects.

You will find complete documentation and demonstration for each kind of transition in the developers' library: https://developer.stupeflix.com/library/?q=tags%3A%22transition%22%20is_featured%3ATrue.

A typical transition tag looks like :

.. code-block:: xml

  <transition type="move" direction="down" duration="1" />

Text
----

============= ============ ========================================================================================================
Attribute     Presence     Description
============= ============ ========================================================================================================
type          required     the type of text effect. The only currently available type is "legend".
duration      optional     the duration of the text tag (optional because it may be inferred from the enclosing stack tag).
============= ============ ========================================================================================================

The text to be displayed is then contained in the text tag:

.. code-block:: xml

  <text type="legend">Here is the text to be displayed</text>

Here is the list of available text effects : :doc:`tutorial/04_text_effects`. And here is the `list of available fonts <https://developer.stupeflix.com/library/?q=fonts%20is_featured%3ATrue>`_.

Audio
-----

============= ============ ========================================================================================================
Attribute     Presence     Description
============= ============ ========================================================================================================
filename      required     an url
duration      optional     overrides the audio file original duration
fadein        optional     starts the audio track with a fade in of the specified duration
fadeout       optional     ends the audio track with a fade out of the specified duration
skip          optional     skip the specified duration in the input file
margin-start  optional     starts the audio track with the specified delay (full duration is usually given by a enclosing node)
margin-end    optional     ends the audio track with the speficied delay before the end (full duration given by the enclosing node)
margin-both   optional     sets both margin. This is exclusive of other "margin" attributes
volume        optional     arbitrary float, sets the volume (default is 1.0)
============= ============ ========================================================================================================

An audio entry example:

.. code-block:: xml

  <audio filename="thriller.mp3" fadein="1.0" fadeout="4.0" skip="2.0" />

Here is a small example on how to use margins:

.. code-block:: xml

  <movie service="craftsman-1.0">
    <body>
      <stack>
        <effect type="panel" duration="15.0">
          <image filename = "http://assets.stupeflix.com/code/images/Ha_long_bay.jpg"/>
        </effect>
        <audio filename="http://dl.dropbox.com/u/1524046/Music/Catch_a_Marvel.mp3" fadeout="2.0" margin-both="2.0" />
      </stack>
    </body>
  </movie>

In that case, the stack tag is assigned the only specified duration, 15.0 seconds. So the audio margins apply on that duration, and audio track is composed of:
* 2.0 seconds of silence
* 9.0 seconds of music
* 2.0 seconds of fade out
* 2.0 seconds of silence

For a total of 15.0 seconds.


Images
------

============= ============ ========================================================================================================
Attribute     Presence     Description
============= ============ ========================================================================================================
filename      required     an url.
color         required     the "#" char followd by a 6 or 8 long RGB(A) hexadecimal string
============= ============ ========================================================================================================

So an image examples are:

.. code-block:: xml

  <image filename="lena.jpg"/>
  <image color="#ff0000"/>
  <image color="#ffffff88"/>

You can too query some Maps to get directly a map image from our Provider Mapbox.

The arguments are center (latitude and longitude) to position the map, zoom (0 means no zoom, you get the whole planisphere), pixel size and an optional marker (latitude and longitude).

An example movie xml is:

.. code-block:: xml

     <image type="map" center="51.526389,-0.160833" zoom="13" markers="51.526389,-0.160833" size="640x640"/>

Supported formats for images are non interlaced pngs, jpeg and non animated gifs.

Videos
------

============= ============ ========================================================================================================
Attribute     Presence     Description
============= ============ ========================================================================================================
filename      required     an url.
============= ============ ========================================================================================================

The most common formats are supported (mpeg2 mpeg4, h264) , for more details see :ref:`supported_codecs` .

Example:

.. code-block:: xml

  <video filename="sunset.mpg"/>

Filters
-------

You will find a complete descriptions of parameters for each kind of filter in `the developers' library <https://developer.stupeflix.com/library/?q=tags:%22filter%22%20is_featured%3ATrue>`_.
