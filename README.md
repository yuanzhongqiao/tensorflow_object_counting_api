<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><div class="markdown-heading" dir="auto"><h1 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TensorFlow 对象计数 API</font></font></h1><a id="user-content-tensorflow-object-counting-api" class="anchor" aria-label="永久链接：TensorFlow 对象计数 API" href="#tensorflow-object-counting-api"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TensorFlow 对象计数 API 是一个构建在 TensorFlow 和 Keras 之上的开源框架，可以轻松开发对象计数系统。</font></font><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您需要专业的超高精度和可靠性的物体检测跟踪计数项目，请联系！</font></font></strong></em></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">快速演示</font></font></h2><a id="user-content-quick-demo" class="anchor" aria-label="永久链接：快速演示" href="#quick-demo"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">累积计数模式（TensorFlow实现）：</font></font></h3><a id="user-content-cumulative-counting-mode-tensorflow-implementation" class="anchor" aria-label="永久链接：累积计数模式（TensorFlow 实现）：" href="#cumulative-counting-mode-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 418px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="418" height="230"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/107875666-4da86080-6ed2-11eb-9be8-cdd0815897cd.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image> <animated-image data-catalyst="" style="width: 400px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="400" height="230"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">实时计数模式（TensorFlow实现）：</font></font></h3><a id="user-content-real-time-counting-mode-tensorflow-implementation" class="anchor" aria-label="永久链接：实时计数模式（TensorFlow 实现）：" href="#real-time-counting-mode-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 410px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="410" height="230"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42237325-1f964e82-7f06-11e8-966b-dfde98701c66.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image> <animated-image data-catalyst="" style="width: 410px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="410" height="230"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42238435-77ac0d34-7f09-11e8-9609-e7c3c2c5af74.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 410px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="410" height="230"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42241094-14163cc8-7f12-11e8-83ed-68021b5e3b33.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image><animated-image data-catalyst="" style="width: 410px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="410" height="230"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42237904-d6a3ac22-7f07-11e8-88f8-5f21430d9503.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<hr>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对象跟踪模式（TensorFlow 实现）：</font></font></h3><a id="user-content-object-tracking-mode-tensorflow-implementation" class="anchor" aria-label="永久链接：对象跟踪模式（TensorFlow 实现）：" href="#object-tracking-mode-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 410px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="410" height="231"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/70389634-4682ea00-19d3-11ea-84a2-3996a43e98fe.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image> <animated-image data-catalyst="" style="width: 410px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="410" height="231"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/70389738-6bc42800-19d4-11ea-971f-f19cb5b90140.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 825px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="814" height="461"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/70389764-e9883380-19d4-11ea-8c54-80935811c3fa.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"></font><a href="https://github.com/kcg2015/Vehicle-Detection-and-Tracking"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">跟踪模块是建立在这种方法</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">之上的</font><font style="vertical-align: inherit;">。</font></font></li>
</ul>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">单图像上的对象计数（TensorFlow 实现）：</font></font></h3><a id="user-content-object-counting-on-single-image-tensorflow-implementation" class="anchor" aria-label="永久链接：单个图像上的对象计数（TensorFlow 实现）：" href="#object-counting-on-single-image-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
<a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/47524870-7c830e80-d8a4-11e8-8fd1-741193615a04.png"><img src="https://user-images.githubusercontent.com/22610163/47524870-7c830e80-d8a4-11e8-8fd1-741193615a04.png" width="750" style="max-width: 100%;"></a></p>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">基于对象计数的 R-CNN（</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/tree/master/mask_rcnn_counting_api"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Keras 和 TensorFlow 实现</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）：</font></font></h3><a id="user-content-object-counting-based-r-cnn-keras-and-tensorflow-implementation" class="anchor" aria-label="永久链接：基于对象计数的 R-CNN（Keras 和 TensorFlow 实现）：" href="#object-counting-based-r-cnn-keras-and-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
<a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/57969852-0569b080-7983-11e9-8051-07d6766ca0e4.png"><img src="https://user-images.githubusercontent.com/22610163/57969852-0569b080-7983-11e9-8051-07d6766ca0e4.png" width="750" style="max-width: 100%;"></a></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">基于 Mask R-CNN 的对象分割和计数（</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/tree/master/mask_rcnn_counting_api"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Keras 和 TensorFlow 实现</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）：</font></font></h3><a id="user-content-object-segmentation--counting-based-mask-r-cnn-keras-and-tensorflow-implementation" class="anchor" aria-label="永久链接：基于 Mask R-CNN 的对象分割和计数（Keras 和 TensorFlow 实现）：" href="#object-segmentation--counting-based-mask-r-cnn-keras-and-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
<a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/57969871-1c100780-7983-11e9-9660-7b8571b01ff7.png"><img src="https://user-images.githubusercontent.com/22610163/57969871-1c100780-7983-11e9-9660-7b8571b01ff7.png" width="750" style="max-width: 100%;"></a></p>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">奖励：自定义对象计数模式（TensorFlow 实现）：</font></font></h3><a id="user-content-bonus-custom-object-counting-mode-tensorflow-implementation" class="anchor" aria-label="永久链接：奖励：自定义对象计数模式（TensorFlow 实现）：" href="#bonus-custom-object-counting-mode-tensorflow-implementation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以使用自己的训练数据训练 TensorFlow 模型，以构建您自己的自定义对象计数器系统！</font><font style="vertical-align: inherit;">如果您想了解如何做到这一点，请查看示例项目之一，其中涵盖了迁移学习的一些理论，并展示了如何将其应用到有用的项目中，如下所示。</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">示例项目#1：蓝精灵计数</font></font></strong></p>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/tree/master/smurf_counter_training"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更多信息可以在这里</font></font></strong></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到</font><font style="vertical-align: inherit;">！</font></font></p>
<p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 750px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="750" height="422"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/62861574-9d6e0080-bd0c-11e9-9e38-b63226df8aa1.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">示例项目#2：Barilla-Spaghetti 计数</font></font></strong></p>
<p dir="auto"><font style="vertical-align: inherit;"></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/tree/master/mask_rcnn_counting_api_keras_tensorflow/barilla_spaghetti_counter_training"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更多信息可以在这里</font></font></strong></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到</font><font style="vertical-align: inherit;">！</font></font></p>
<p align="center" dir="auto">
  <a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/62903429-46e3df00-bd6b-11e9-9f97-4de477fa8769.png"><img src="https://user-images.githubusercontent.com/22610163/62903429-46e3df00-bd6b-11e9-9f97-4de477fa8769.png" width="750" style="max-width: 100%;"></a>  
</p>
<hr>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">发展正在进步！</font><font style="vertical-align: inherit;">API即将更新，更优秀、更轻量级的API将在本仓库中提供！</font></font></strong></em></p>
<ul dir="auto">
<li><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将添加详细的 API 文档和解释 API 基本用法的示例 jupyter 笔记本！</font></font></strong></em></li>
</ul>
<p dir="auto"><strong><font style="vertical-align: inherit;"></font><a href="https://github.com/ahmetozlu/vehicle_counting_tensorflow"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以在此存储库</font></font></em></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中找到使用 TensorFlow 对象计数 API 的示例项目 - 案例研究</font><font style="vertical-align: inherit;">。</font></font></strong></p>
<hr>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用法</font></font></h2><a id="user-content-usage" class="anchor" aria-label="永久链接：用途" href="#usage"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.)“累计计数模式”的使用</font></font></h3><a id="user-content-1-usage-of-cumulative-counting-mode" class="anchor" aria-label="固定链接： 1.) “累计计数模式”的使用" href="#1-usage-of-cumulative-counting-mode"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.1) 用于检测、跟踪和统计</font><font style="vertical-align: inherit;">禁用颜色预测的</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">行人</font></font></em><font style="vertical-align: inherit;"></font></h4><a id="user-content-11-for-detecting-tracking-and-counting-the-pedestrians-with-disabled-color-prediction" class="anchor" aria-label="永久链接：1.1）用于检测、跟踪和计数禁用颜色预测的行人" href="#11-for-detecting-tracking-and-counting-the-pedestrians-with-disabled-color-prediction"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“行人计数”案例中“累积计数模式”的用法：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects
roi = 385 # roi line position
deviation = 1 # the constant that represents the object counting area

object_counting_api.cumulative_object_counting_x_axis(input_video, detection_graph, category_index, is_color_recognition_enabled, roi, deviation) # counting all the objects
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects
roi = 385 # roi line position
deviation = 1 # the constant that represents the object counting area

object_counting_api.cumulative_object_counting_x_axis(input_video, detection_graph, category_index, is_color_recognition_enabled, roi, deviation) # counting all the objects" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“行人计数”案例的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="403"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/43166945-c0744de0-8fa0-11e8-8985-9f863c59e859.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<hr>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“行人计数案例研究”源代码：</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/blob/master/pedestrian_counting.py"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">pedestrian_counting.py</font></font></a></strong></p>
<hr>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">1.2)</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用于检测、跟踪和统计</font><font style="vertical-align: inherit;">启用颜色预测的</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">车辆</font></font></em><font style="vertical-align: inherit;"></font></p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“车辆统计”案例中“累计统计模式”的使用：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = True # set it to true for enabling the color prediction for the detected objects
roi = 200 # roi line position
deviation = 3 # the constant that represents the object counting area

object_counting_api.cumulative_object_counting_y_axis(input_video, detection_graph, category_index, is_color_recognition_enabled, roi, deviation) # counting all the objects
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = True # set it to true for enabling the color prediction for the detected objects
roi = 200 # roi line position
deviation = 3 # the constant that represents the object counting area

object_counting_api.cumulative_object_counting_y_axis(input_video, detection_graph, category_index, is_color_recognition_enabled, roi, deviation) # counting all the objects" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“车辆统计”案例的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="385"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/43166455-45964aac-8f9f-11e8-9ddf-f71d05f0c7f5.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<hr>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“车辆计数案例研究”源代码：</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/blob/master/vehicle_counting.py"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">vehicle_counting.py</font></font></a></strong></p>
<hr>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.) “实时计数模式”的使用</font></font></h3><a id="user-content-2-usage-of-real-time-counting-mode" class="anchor" aria-label="永久链接：2.)“实时计数模式”的使用" href="#2-usage-of-real-time-counting-mode"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.1) 用于检测、跟踪和计数</font><font style="vertical-align: inherit;">禁用颜色预测</font></font><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的目标对象</font></font></em><font style="vertical-align: inherit;"></font></h4><a id="user-content-21-for-detecting-tracking-and-counting-the-targeted-objects-with-disabled-color-prediction" class="anchor" aria-label="永久链接：2.1）用于检测、跟踪和计数禁用颜色预测的目标对象" href="#21-for-detecting-tracking-and-counting-the-targeted-objects-with-disabled-color-prediction"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“目标对象是自行车”的用法：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects
targeted_objects = "bicycle" 

object_counting_api.targeted_object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled, targeted_objects) # targeted objects counting
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects
targeted_objects = &quot;bicycle&quot; 

object_counting_api.targeted_object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled, targeted_objects) # targeted objects counting" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“目标对象是自行车”的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="394"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42411751-1ae1d3f0-820a-11e8-8465-9ec9b44d4fe7.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“目标对象是人”的用法：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects
targeted_objects = "person"

object_counting_api.targeted_object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled, targeted_objects) # targeted objects counting
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects
targeted_objects = &quot;person&quot;

object_counting_api.targeted_object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled, targeted_objects) # targeted objects counting" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“目标对象是人”的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="394"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42411749-1a80362c-820a-11e8-864e-acdeed85b1f2.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“检测、计数和跟踪所有物体”的用法：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects

object_counting_api.object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled) # counting all the objects
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects

object_counting_api.object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled) # counting all the objects" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“检测、计数和跟踪所有物体”的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="394"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42411750-1aae0d72-820a-11e8-8726-4b57480f4cb8.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<hr>
<p dir="auto"><em><font style="vertical-align: inherit;"></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“检测、计数和跟踪多个目标物体</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">”的用法</font><font style="vertical-align: inherit;">：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>targeted_objects = "person, bicycle" # (for counting targeted objects) change it with your targeted objects
is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects

object_counting_api.targeted_object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled, targeted_objects) # targeted objects counting
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="targeted_objects = &quot;person, bicycle&quot; # (for counting targeted objects) change it with your targeted objects
is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects

object_counting_api.targeted_object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled, targeted_objects) # targeted objects counting" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<hr>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">2.2) 用于检测、跟踪和计数“所有禁用颜色预测的对象”</font></font></h4><a id="user-content-22-for-detecting-tracking-and-counting-all-the-objects-with-disabled-color-prediction" class="anchor" aria-label="永久链接：2.2）用于检测、跟踪和计数“所有禁用颜色预测的对象”" href="#22-for-detecting-tracking-and-counting-all-the-objects-with-disabled-color-prediction"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">检测、计数和跟踪“所有禁用颜色预测的对象”的用法：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects

object_counting_api.object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled) # counting all the objects
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = False # set it to true for enabling the color prediction for the detected objects

object_counting_api.object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled) # counting all the objects" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对“所有禁用颜色预测的对象”进行检测、计数和跟踪的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="394"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42411748-1a5ab49c-820a-11e8-8648-d78ffa08c28c.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">检测、计数和跟踪“所有启用颜色预测的对象”的用法：</font></font></em></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>is_color_recognition_enabled = True # set it to true for enabling the color prediction for the detected objects

object_counting_api.object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled) # counting all the objects
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="is_color_recognition_enabled = True # set it to true for enabling the color prediction for the detected objects

object_counting_api.object_counting(input_video, detection_graph, category_index, is_color_recognition_enabled) # counting all the objects" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">检测、计数和跟踪“所有启用颜色预测的对象”的结果：</font></font></em></p>
 <p align="center" dir="auto">
  <animated-image data-catalyst="" style="width: 700px;"><a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" data-target="animated-image.originalLink"><img src="https://user-images.githubusercontent.com/22610163/42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" style="max-width: 100%; display: inline-block;" data-target="animated-image.originalImage"></a>
      <span class="AnimatedImagePlayer" data-target="animated-image.player" hidden="">
        <a data-target="animated-image.replacedLink" class="AnimatedImagePlayer-images" href="https://user-images.githubusercontent.com/22610163/42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" target="_blank">
          
        <span data-target="animated-image.imageContainer">
            <img data-target="animated-image.replacedImage" alt="42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" class="AnimatedImagePlayer-animatedImage" src="https://user-images.githubusercontent.com/22610163/42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" style="display: block; opacity: 1;">
          <canvas class="AnimatedImagePlayer-stillImage" aria-hidden="true" width="700" height="394"></canvas></span></a>
        <button data-target="animated-image.imageButton" class="AnimatedImagePlayer-images" tabindex="-1" aria-label="Play 42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" hidden=""></button>
        <span class="AnimatedImagePlayer-controls" data-target="animated-image.controls" hidden="">
          <button data-target="animated-image.playButton" class="AnimatedImagePlayer-button" aria-label="Play 42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif">
            <svg aria-hidden="true" focusable="false" class="octicon icon-play" width="16" height="16" viewBox="0 0 16 16" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M4 13.5427V2.45734C4 1.82607 4.69692 1.4435 5.2295 1.78241L13.9394 7.32507C14.4334 7.63943 14.4334 8.36057 13.9394 8.67493L5.2295 14.2176C4.69692 14.5565 4 14.1739 4 13.5427Z">
            </path></svg>
            <svg aria-hidden="true" focusable="false" class="octicon icon-pause" width="16" height="16" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg">
              <rect x="4" y="2" width="3" height="12" rx="1"></rect>
              <rect x="9" y="2" width="3" height="12" rx="1"></rect>
            </svg>
          </button>
          <a data-target="animated-image.openButton" aria-label="Open 42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif in new window" class="AnimatedImagePlayer-button" href="https://user-images.githubusercontent.com/22610163/42411747-1a215e4a-820a-11e8-8aef-faa500df6836.gif" target="_blank">
            <svg aria-hidden="true" class="octicon" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" width="16" height="16">
              <path fill-rule="evenodd" d="M10.604 1h4.146a.25.25 0 01.25.25v4.146a.25.25 0 01-.427.177L13.03 4.03 9.28 7.78a.75.75 0 01-1.06-1.06l3.75-3.75-1.543-1.543A.25.25 0 0110.604 1zM3.75 2A1.75 1.75 0 002 3.75v8.5c0 .966.784 1.75 1.75 1.75h8.5A1.75 1.75 0 0014 12.25v-3.5a.75.75 0 00-1.5 0v3.5a.25.25 0 01-.25.25h-8.5a.25.25 0 01-.25-.25v-8.5a.25.25 0 01.25-.25h3.5a.75.75 0 000-1.5h-3.5z"></path>
            </svg>
          </a>
        </span>
      </span></animated-image>
</p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">3.) “对象跟踪模式”的使用</font></font></h3><a id="user-content-3-usage-of-object-tracking-mode" class="anchor" aria-label="永久链接：3.) “对象跟踪模式”的使用" href="#3-usage-of-object-tracking-mode"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">只需运行</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/blob/master/object_tracking.py"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">object_tracking.py</font></font></a></p>
<hr>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“实时计数模式”的使用示例：</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/blob/master/real_time_counting.py"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">real_time_counting.py</font></font></a></strong></p>
<hr>
<p dir="auto"><em><font style="vertical-align: inherit;"></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/blob/master/utils/visualization_utils.py#L443"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以在此行中</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以百分比形式</font><font style="vertical-align: inherit;">设置最小对象检测阈值。</font><font style="vertical-align: inherit;">默认最小物体检测阈值是 0.5！</font></font></em></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TensorFlow 对象计数 API 的一般功能</font></font></h2><a id="user-content-general-capabilities-of-the-tensorflow-object-counting-api" class="anchor" aria-label="永久链接：TensorFlow 对象计数 API 的一般功能" href="#general-capabilities-of-the-tensorflow-object-counting-api"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/48421361-6662c280-e76d-11e8-9680-ec86e245fdac.jpg"><img src="https://user-images.githubusercontent.com/22610163/48421361-6662c280-e76d-11e8-9680-ec86e245fdac.jpg" width="720" style="max-width: 100%;"></a>
</p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下是 TensorFlow 对象计数 API 的一些很酷的功能：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">仅检测目标对象</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">检测所有物体</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">仅计算目标对象</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数出所有物体的数量</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">预测目标物体的颜色</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">预测所有物体的颜色</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">预测目标物体的速度</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">预测所有物体的速度</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将检测计数结果打印为 .csv 文件作为分析报告</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将检测到的对象保存为新图像并存储在</font></font><a href="/ahmetozlu/tensorflow_object_counting_api/blob/master/www"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Detected_object文件夹下</font></font></a></li>
<li><font style="vertical-align: inherit;"><a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md"><font style="vertical-align: inherit;">选择、下载和使用由 Google Brain 团队训练的</font></a><font style="vertical-align: inherit;">最先进模型</font></font><a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md"><font style="vertical-align: inherit;"></font></a></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用</font></font><a href="https://www.tensorflow.org/guide/keras" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您自己训练的模型</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><a href="https://github.com/Hvass-Labs/TensorFlow-Tutorials/blob/master/10_Fine-Tuning.ipynb"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">微调的模型</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">来检测特定对象</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将检测和计数结果保存为新视频或实时显示检测和计数结果</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">根据您的要求处理图像或视频</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下是 TensorFlow 对象计数 API 的一些很酷的架构设计功能：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">轻量级，实时运行</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可扩展且设计良好的框架，易于使用</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">获得“Pythonic 方法”的优势</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">它支持 REST 架构和 RESTful Web 服务</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">待办事项：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将提供 TensorFlox2.x 支持。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将开发自主训练图像注释工具。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将开发GUI。</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">理论</font></font></h2><a id="user-content-theory" class="anchor" aria-label="永久链接：理论" href="#theory"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">系统架构</font></font></h3><a id="user-content-system-architecture" class="anchor" aria-label="永久链接：系统架构" href="#system-architecture"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/48421362-6662c280-e76d-11e8-9b63-da9698626f75.jpg"><img src="https://user-images.githubusercontent.com/22610163/48421362-6662c280-e76d-11e8-9b63-da9698626f75.jpg" width="720" style="max-width: 100%;"></a>
</p>
<ul dir="auto">
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对象检测和分类是在 TensorFlow 对象检测 API 之上开发的，</font></font><a href="https://github.com/tensorflow/models/tree/master/research/object_detection"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参考资料 获取更多信息。</font></font></p>
</li>
<li>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">对象颜色预测是使用 OpenCV 通过 K 最近邻机器学习分类算法开发的，该算法是经过训练的颜色直方图特征，</font></font><a href="https://github.com/ahmetozlu/tensorflow_object_counting_api/tree/master/utils/color_recognition_module"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参考资料 获取更多信息。</font></font></p>
</li>
</ul>
<p dir="auto"><a href="https://www.tensorflow.org/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TensorFlow™</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是一个使用数据流图进行数值计算的开源软件库。</font><font style="vertical-align: inherit;">图中的节点表示数学运算，而图的边表示它们之间通信的多维数据数组（张量）。</font></font></p>
<p dir="auto"><a href="https://opencv.org/about.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">OpenCV（开源计算机视觉库）</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">是一个开源计算机视觉和机器学习软件库。</font><font style="vertical-align: inherit;">OpenCV 旨在为计算机视觉应用提供通用基础设施，并加速机器感知在商业产品中的使用。</font></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">追踪器</font></font></h3><a id="user-content-tracker" class="anchor" aria-label="永久链接：追踪器" href="#tracker"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/41812993-a4b5a172-7735-11e8-89f6-083ec0625f21.png"><img src="https://user-images.githubusercontent.com/22610163/41812993-a4b5a172-7735-11e8-89f6-083ec0625f21.png" width="700" style="max-width: 100%;"></a>
</p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 OpenCV 逐帧读取源视频。</font><font style="vertical-align: inherit;">每个帧均由在 TensorFlow 上开发的</font></font><a href="http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“SSD with Mobilenet”模型</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">处理。</font><font style="vertical-align: inherit;">这是一个循环，一直持续到视频结束。</font><font style="vertical-align: inherit;">Tracker的主要流程如上图所示。</font></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">楷模</font></font></h3><a id="user-content-models" class="anchor" aria-label="永久链接：模型" href="#models"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p align="center" dir="auto">
  <a target="_blank" rel="noopener noreferrer nofollow" href="https://user-images.githubusercontent.com/22610163/48481757-b1d5a900-e81f-11e8-824b-4317115fe5b4.png"><img src="https://user-images.githubusercontent.com/22610163/48481757-b1d5a900-e81f-11e8-824b-4317115fe5b4.png" style="max-width: 100%;"></a>
</p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">默认情况下，我在此项目中使用</font></font><a href="http://download.tensorflow.org/models/object_detection/ssd_mobilenet_v1_coco_2017_11_17" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">“SSD with Mobilenet”模型</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font><a href="https://towardsdatascience.com/understanding-ssd-multibox-real-time-object-detection-in-deep-learning-495ef744fab" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以在这里</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">找到有关 SSD 的更多信息</font><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅</font></font><a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">检测模型动物园</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，了解可以以不同的速度和精度开箱即用运行的其他模型的列表。</font><font style="vertical-align: inherit;">您可以使用 TensorFlow 对象检测 API 轻松选择、下载和使用适合您需求的最先进模型。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以在训练有素的 TensorFlow 模型上执行迁移学习，以构建您的自定义对象计数系统！</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">项目演示</font></font></h2><a id="user-content-project-demo" class="anchor" aria-label="永久链接：项目演示" href="#project-demo"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该项目的演示视频可在</font></font><a href="https://www.youtube.com/watch?v=bas6c8d1JyU" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">我的 YouTube 频道</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">上观看。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装</font></font></h2><a id="user-content-installation" class="anchor" aria-label="永久链接：安装" href="#installation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">依赖关系</font></font></h3><a id="user-content-dependencies" class="anchor" aria-label="永久链接：依赖关系" href="#dependencies"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Tensorflow 对象计数 API 依赖于以下库（请参阅</font></font><a href="/ahmetozlu/tensorflow_object_counting_api/blob/master"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">requirements.txt</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）：</font></font></p>
<ul dir="auto">
<li><a href="https://github.com/tensorflow/models/tree/master/research/object_detection"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">TensorFlow 对象检测 API</font></font></a></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">张量流==1.5.0</font></font></strong></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">喀拉斯==2.0.8</font></font></strong></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">opencv-python==4.4.0.42</font></font></strong></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">协议缓冲区 3.0.0</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Python-tk</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">枕头1.0</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">lxml</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">tf Slim（包含在“tensorflow/models/research/”结账中）</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Jupyter笔记本</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Matplotlib</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">赛通</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">上下文库2</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可可API</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">有关安装 Tensorflow 的详细步骤，请按照</font></font><a href="https://www.tensorflow.org/install/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Tensorflow 安装说明</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">进行操作。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">必须安装 TensorFlow 对象检测 API 才能运行 TensorFlow 对象计数 API，有关更多信息，请参阅</font></font><a href="https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">此</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重要提示：TensorFlow2版本导致的兼容性问题。</font></font></h3><a id="user-content-important-compatibility-problems-caused-by-tensorflow2-version" class="anchor" aria-label="永久链接：重要提示：TensorFlow2 版本导致的兼容性问题。" href="#important-compatibility-problems-caused-by-tensorflow2-version"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">本项目使用TensorFlow 1.5.0版本开发。</font><font style="vertical-align: inherit;">如果您需要使用 TensorFlow 2.x 版本运行此项目，只需将 tensorflow 导入替换为tensorflow.compat.v1，并添加 tf.disable_v2_behavior 即可。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">而不是这个导入语句：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>import tensorflow
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="import tensorflow" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用这个：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="import tensorflow.compat.v1 as tf
tf.disable_v2_behavior()" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">引文</font></font></h2><a id="user-content-citation" class="anchor" aria-label="永久链接：引文" href="#citation"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您在出版物中使用此代码，请将其引用为：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>@ONLINE{
    author = "Ahmet Özlü",
    title  = "TensorFlow Object Counting API",
    year   = "2018",
    url    = "https://github.com/ahmetozlu/tensorflow_object_counting_api"
}
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="@ONLINE{
    author = &quot;Ahmet Özlü&quot;,
    title  = &quot;TensorFlow Object Counting API&quot;,
    year   = &quot;2018&quot;,
    url    = &quot;https://github.com/ahmetozlu/tensorflow_object_counting_api&quot;
}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">作者</font></font></h2><a id="user-content-author" class="anchor" aria-label="永久链接： 作者" href="#author"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">艾哈迈德·厄兹鲁</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执照</font></font></h2><a id="user-content-license" class="anchor" aria-label="永久链接：许可证" href="#license"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该系统可在 MIT 许可下使用。</font><font style="vertical-align: inherit;">有关详细信息，请参阅许可证文件。</font></font></p>
</article></div>
