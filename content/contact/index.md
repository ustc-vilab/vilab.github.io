---
title: Contact
date: 2022-10-24

type: landing

sections:
  - block: contact
    content:
      title: Contact
      text: |-
        ViLab专注“让机器在高速、低光、多模态场景下看得清、看得懂”。近三年围绕事件相机、自动驾驶生成、联邦视觉学习，在CCF-A会议/期刊发表论文10余篇。欢迎对计算机视觉、机器学习、智能系统感兴趣的本科实习生、推免生、博士生与博士后加入，一起把前沿算法写进真实世界。
      email: sunxiaoyan@ustc.edu.cn
      address:
        street: 100 Fuxing Road
        city: Hefei
        region: Anhui
        postcode: '230031'
        country: China
        country_code: CN
      coordinates:
        latitude: '31.8217'
        longitude: '117.12'
      appointment_url: 'https://calendly.com'
      #contact_links:
      #  - icon: comments
      #    icon_pack: fas
      #    name: Discuss on Forum
      #    link: 'https://discourse.gohugo.io'
  
      # Automatically link email and phone or display as text?
      autolink: true
  
      # Email form provider
      form:
        provider: netlify
        formspree:
          id:
        netlify:
          # Enable CAPTCHA challenge to reduce spam?
          captcha: false
    design:
      columns: '1'

  - block: markdown
    content:
      title:
      subtitle: ''
      text:
    design:
      columns: '1'
      background:
        image: 
          filename: contact.jpg
          filters:
            brightness: 1
          parallax: false
          position: center
          size: cover
          text_color_light: true
      spacing:
        padding: ['20px', '0', '20px', '0']
      css_class: fullscreen
---
