ph-audio-image-video-recorder
================

This component can be used to record audio and video from the devices microphones and cameras. It uses only the
standard APIs **Web Audio API** and **UserMedia API**. It also overlays the live video output with a audio visualization.

Please note that this component is a fancy wrapper around those APIs and provides you with the essential functionality
for recording video and audio. There are also some filters added, which the user can apply on the video. These filters
are merged into the video stream. They're only applied via the CSS3 selector `filter`.
The APIs are at this time (January 2015) not well supported by the majority of the browsers available. Please use with
caution and don't use it in production :)

Please note that the audio and video stream can not be recorded as one blob record containing audio and video in one
blob. This is caused by the API limitation. As a result of that a video exists of a recorded video stream and a
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