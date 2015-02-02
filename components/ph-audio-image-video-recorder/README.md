ph-audio-image-video-recorder
================

This component gives you the ability to record audio and video **with just HTML standards** and without any additional 
plugins. This component gives you a (a not yet responsive) GUI interface to...

* record video (GetUserMedia/Stream API + Canvas + Whammy.js),
* record audio (GetUserMedia/Stream API + Web Audio API + Recorder.js),
* capture images (GetUserMedia/Stream API + HTMLCanvasElement)

from the available devices the browser makes available through the **MediaStreamTrack API**.

To record audio without any additional plugins the **Web Audio API** is used to build audio nodes. These nodes are also
used to visualize the microphone input.

Please note that this component is a fancy wrapper around those APIs and provides you with the essential functionality
for recording video and audio which is (not yet available) through Web APIs only. So these component uses Whammy.js to
build a video blob from single canvas frames and Recorder.js to create an audio blob in WAVE format.

The APIs are (as of January 2015) not well supported by the majority of the browsers available. Please use with
caution and don't use it in production :) Chrome seems to be the only browser with acceptable performance and support.

The audio and video stream can not be recorded as one blob record containing the audio and video source in one file.
This is caused by the API limitation. Due to this a video exists of a recorded video stream and a
separate recorded audio stream. The recorded audio and video will be started at the same time, when the user starts to
play a recorded video. So it's possible that the video and audio will run out of sync.

Use the attribute `mode` to switch between the types of recording (video (audio+video), audio (only audio), image).

== **Please Note** ==

This component only works on those browsers:

- iOS 8+ on Safari only supports the Audio WebAPI, so there's no Video/Image access available
- Android 4.4.4+ on Chrome 40+ supports Audio and Video, 5+ integrates the evergreen Chrome, so it works there too
- Windows Internet Explorer does NOT support any of the used APIs

## 1. Install

`bower install silentHoo/ph-audio-image-video-recorder`

Run the command above from your project root.

## 2. Import

Import the component by adding this to your HTML file:

`<link rel="import" href="components/ph-audio-image-video-recorder/ph-audio-image-video-recorder.html">`

## 3. Use / Demo

See the [component page](http://silentHoo.github.io/ph-audio-image-video-recorder) for more information.

## Dependency Graph

To give you an overview of the dependencies (resolved by bower), here is a sketch:

![The ph-audio-image-video-recorder dependency graph.](http://silentHoo.github.io/ph-audio-image-video-recorder/dependency-graph.svg "The ph-audio-image-video-recorder dependency graph.")

## License

Copyright (c) 2014-2015 Patrick Hillert. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

1. Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.
2. Redistributions in binary form must reproduce the above
copyright notice, this list of conditions and the following disclaimer
in the documentation and/or other materials provided with the
distribution.
3. Neither the name of the copyright holder nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.