---
layout: post
title: "Install CentOS 6.5"
date: 2014-04-06 15:30:01
categories: jekyll update
---

  透過 USB flash drive 來安裝 CentOS (適用 CentOS 6.5+)
  
  找一台有安裝 Linux 作業系統的電腦, 下載 [CentOS DVD 映像檔][fn2]. 你只須 DVD1 就能完成安裝, DVD2 內只包含附加的 RPM，你可以按需要在日後安裝它們。
  安裝程式在安裝時不會徵用 [DVD2][fn3]. 

  在此我們假設下載的版本是 CentOS x86\_64. 下載完後 cd 到下載目錄. 

  接著, 插入 USB flash drive (建議用 USB3.0 同時讀速最好有 30MB +), 並用指令 fdisk 來確認 USB flash drive 位置.

  {% highlight bash %}

  # fdisk -l
  
  {% endhighlight %}

  在此假設查詢到的位置是 /dev/sdb

  最後執行下列[指令][fn1] 來製作 bootable USB flash drive.

  {% highlight bash %}
  
  # dd if=CentOS-6.5-x86\_64-bin-DVD1.iso of=/dev/sdb
	
  {% endhighlight %}
     
  其作業時間視 USB flash drive 的寫速決定.

  完成就可以用該 USB flash drive 來安裝 CentOS. 安裝前記得調整開機裝置順序, 選取 hard disk (or USB HDD) 為第一順位. 
  進入安裝後, 當詢問資料來源時, 指向對應的 USB flash drive 即可. 

  [fn1] 指令來自 http://wiki.centos.org/zh-tw/HowTos/InstallFromUSBkey

  [fn2] 下載網址: http://isoredirect.centos.org/centos/6/isos/x86\_64/CentOS-6.5-x86\_64-bin-DVD1.iso

  [fn3] 請見 http://wiki.centos.org/zh-tw/Manuals/ReleaseNotes/CentOS6.5 or 這篇 http://mirrors.xmission.com/centos/6.5/isos/i386/README.txt
