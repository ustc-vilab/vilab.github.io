---
title:
type: landing
sections:
  - block: markdown
    content:
      title: ''
      subtitle: ''
      text: |
        <style>
          /* 轮播容器高度可按需调 */
          .hero-wrap,
          .section-two {
            max-width: 1360px;
            margin: 0 auto 24px;
          }

          /* 轮播容器自适应图片高度，不裁剪 */
          .hero-slider {
            position: relative;
            overflow: hidden;
            border-radius: 6px;
            width: 100%;
            max-width: 1360px;   /* 与下方两栏同宽，可按需调整 */
            margin: 0 auto;
            background: #000;    /* 可换成你要的底色，用于未占满时的背景 */
          }

          .hero-slides { display: flex; transition: transform 0.6s ease; }
          .hero-slide { flex: 1 0 100%; display: flex; justify-content: center; }
          .hero-slide img {
            width: 100%;
            height: auto;        /* 让高度随图片比例自适应 */
            display: block;
            object-fit: contain; /* 不裁剪高度，完整显示图片 */
          }
          .hero-caption {
            position: static;
            display: block;
            background: rgb(0, 112, 192);
            color: #fff;
            padding: 12px 16px;
            font-weight: 700;
            font-size: 1.1rem; /* 与顶栏菜单同尺寸 */
            text-align: left;
            margin-top: 0;
          }
          .hero-btn {
            position: absolute; top: 50%; transform: translateY(-50%);
            background: rgba(0,0,0,0.35); color: #fff;
            border: none; width: 34px; height: 34px; border-radius: 50%;
            cursor: pointer; font-size: 18px; line-height: 34px;
          }
          .hero-btn:hover { background: rgba(0,0,0,0.55); }
          .hero-btn.prev { left: 10px; }
          .hero-btn.next { right: 10px; }
          .hero-dots {
            position: absolute; right: 12px; bottom: 10px;
            display: flex; gap: 6px;
          }
          .hero-dot {
            width: 10px; height: 10px; border-radius: 50%;
            background: rgba(255,255,255,0.5); border: 1px solid rgba(0,0,0,0.15);
            cursor: pointer;
          }
          .hero-dot.active { background: #fff; }

          /* 左右两栏比例 1:1 */
          .section-two { display: grid; grid-template-columns: 6fr 4fr; gap: 24px; align-items: start; }
          .intro-card, .news-card {
            background: #fff; border: 1px solid #e5e5e5; border-radius: 4px; padding: 16px 18px;
          }
          .intro-card h3, .news-card h3 {
            margin-top: 0;
            font-size: 1.1rem;
            font-family: "SimHei", "Microsoft YaHei", "Helvetica Neue", Arial, sans-serif;
            font-weight: 700;
          }

          /* 实验室图片等比显示，不裁剪 */
          .intro-img { margin: 8px -18px 12px; }
          .intro-img img {
            width: 100%; height: auto; display: block;
            object-fit: contain; max-width: 100%; image-rendering: auto;
          }

          .news-list { list-style: none; padding: 0; margin: 0; }
          .news-list li { display: flex; align-items: center; justify-content: space-between; padding: 20px 0; border-bottom: 1px solid #f1f1f1; }
          .news-list a { color: #00529b; text-decoration: none; line-height: 1.3; margin-right: 8px; flex: 0 0 70%; }
          .news-date { color: #888; font-size: 13px; margin-left: 12px; white-space: nowrap; }
          .news-thumb { flex: 0 0 30%; }
          .news-thumb img {
            width: 100%;
            height: auto;
            display: block;
            border-radius: 3px;
            object-fit: cover;
          }

          @media(max-width: 900px) {
            .section-two { grid-template-columns: 1fr; }
            .hero-wrap { margin: 0 0 16px; max-width: 100%; }
            .hero-slide img { max-height: 260px; }
            .hero-caption { font-size: 14px; }
          }
        </style>

        <div class="hero-wrap">
          <div class="hero-slider" id="hero-slider">
            <div class="hero-slides">
              <div class="hero-slide"><img data-src="/media/biomedical_imaging_technology.png" data-caption="生物医学图像" alt="slide 1"></div>
              <div class="hero-slide"><img data-src="/media/video_coding.png" data-caption="视频编码" alt="slide 2"></div>
              <div class="hero-slide"><img data-src="/media/video_understanding.png" data-caption="视频理解" alt="slide 3"></div>
              <div class="hero-slide"><img data-src="/media/neuromorphic.png" data-caption="类脑计算" alt="slide 4"></div>
            </div>
            <div class="hero-caption" id="hero-caption">Neuromorphic Computing</div>
            <button class="hero-btn prev" aria-label="Previous slide">‹</button>
            <button class="hero-btn next" aria-label="Next slide">›</button>
            <div class="hero-dots"></div>
          </div>
        </div>

        <div class="section-two">
          <div class="intro-card">
            <h3>实验室简介</h3>
            <div class="intro-img">
              <img src="/media/welcome.jpg" alt="group photo">
            </div>
          <p>视觉智能实验室（ViLab）隶属于类脑智能技术及应用国家工程实验室，由孙晓艳教授在中国科学技术大学一手创建。实验室面向人工智能中的重难点问题展开研究，承接多项重大科研项目。目前实验室的主要研究方向如：多模态图像视频理解、事件相机、音视频编码、医学图像处理。<br>
          实验室现有教授1名，副研究员1名，博士后1名，博士研究生19名，硕士研究生26名以及若干毕业生。实验室科研经费充足，研究氛围自由活跃，计算机资源充足、在各大期刊会议发表多篇论文，产出稳定。实验室多名同学在头部大厂和研究机构进行交流学习，欢迎你的加入！</p>
          </div>

          <div class="news-card">
            <h3>新闻</h3>
            {{< event_news 7 >}}
          </div>
        </div>

        <script>
          (() => {
            const slider = document.getElementById('hero-slider');
            if (!slider) return;
            const slidesWrap = slider.querySelector('.hero-slides');
            const slides = Array.from(slider.querySelectorAll('.hero-slide'));
            const dotsWrap = slider.querySelector('.hero-dots');
            const prevBtn = slider.querySelector('.hero-btn.prev');
            const nextBtn = slider.querySelector('.hero-btn.next');
            const captionEl = slider.querySelector('#hero-caption');
            const intervalMs = 8000; // 8 秒一张
            let timer = null;
            let index = 0;

            // lazy load（不再因为 onerror 隐藏整张图）
            slides.forEach(s => {
              const img = s.querySelector('img');
              if (img && img.dataset.src) {
                img.src = img.dataset.src;
                img.removeAttribute('data-src');
              }
            });

            // build dots
            slides.forEach((_, i) => {
              const d = document.createElement('button');
              d.className = 'hero-dot' + (i === 0 ? ' active' : '');
              d.setAttribute('aria-label', 'Go to slide ' + (i + 1));
              d.addEventListener('click', () => goTo(i));
              dotsWrap.appendChild(d);
            });

            const dots = Array.from(dotsWrap.querySelectorAll('.hero-dot'));

            function updateCaption(i) {
              const s = slides[i];
              if (!s) return;
              const img = s.querySelector('img');
              const text = (img && img.dataset.caption) || img?.alt || '';
              if (captionEl) captionEl.textContent = text;
            }

            function goTo(i) {
              const realIndex = Math.max(0, Math.min(i, slides.length - 1));
              index = realIndex;
              slidesWrap.style.transform = `translateX(-${realIndex * 100}%)`;
              dots.forEach((d, k) => d.classList.toggle('active', k === realIndex));
              updateCaption(realIndex);
              resetTimer();
            }

            function next() { goTo((index + 1) % slides.length); }
            function prev() { goTo((index - 1 + slides.length) % slides.length); }

            function resetTimer() {
              if (timer) clearInterval(timer);
              timer = setInterval(next, intervalMs);
            }

            prevBtn.addEventListener('click', prev);
            nextBtn.addEventListener('click', next);
            slider.addEventListener('mouseenter', () => timer && clearInterval(timer));
            slider.addEventListener('mouseleave', resetTimer);

            goTo(0);
            resetTimer();
          })();
        </script>
---