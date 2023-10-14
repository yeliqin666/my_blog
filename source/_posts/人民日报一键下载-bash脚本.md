---
uuid: b358d9ab-20ce-a38e-f1a0-f3aa0acebe1c
title: 人民日报一键下载-bash脚本
date: 2023-09-12 13:28:17
author: yeliqin666
tags:
- 报刊
categories:
- 资源
---
这是我高三的某个晚上写的小脚本，用于下载人民日报国内版与国外版报纸PDF，包括分版与合并版

虽然报纸没读过几次...但这么丢了也可惜，分享给大伙使用

依赖于pdftk实现页面合并，报纸资源来自人民日报官网，侵删

<!-- more -->
代码如下
```
#!/bin/bash
clear && packs=$(dpkg -s pdftk)
	if ! echo $packs | grep -q "install ok installed" > /dev/null ;then
		echo -e "\033[31m  安装pdftk \033[0m"
		${su} apt-get install pdftk -y
	fi
read -p "请输入下载报纸的日期：(eg. 20220930)" pdate
pdate=${1}
rm -rf ${pdate}-国内_split ${pdate}-海外_split && mkdir ${pdate}-国内_split ${pdate}-海外_split
i=1
echo 开始获取$pdate人民日报国内版
while :
do
	if [[ "$(expr length $i)" == "1" ]] ; then i=0${i};fi
	purl="http://paper.people.com.cn/rmrb/images/$(echo $pdate|cut -c 1-4)-$(echo $pdate|cut -c 5-6)/$(echo $pdate|cut -c 7-8)/$i/rmrb${pdate}$i.pdf"
	if [[ "$(curl -o /dev/null --connect-timeout 3 -s -w "%{http_code}" $purl)" == "200" ]];then
		echo 获取第$i版中...
		wget $purl -O ${pdate}-国内_split/RMRB${pdate}第$i版.pdf  > /dev/null 2>&1
	else
		break
	fi
i=$((10#$i + 1))
done
echo "合并中..."
pdftk ${pdate}-国内_split/*.pdf output 人民日报${pdate}_国内.pdf
i=1
echo 开始获取$pdate人民日报海外版
while :
do
	if [[ "$(expr length $i)" == "1" ]] ; then i=0${i};fi
	purl="http://paper.people.com.cn/rmrbhwb/images/$(echo $pdate|cut -c 1-4)-$(echo $pdate|cut -c 5-6)/$(echo $pdate|cut -c 7-8)/$i/rmrbhwb${pdate}$i.pdf"
	if [[ "$(curl -o /dev/null --connect-timeout 3 -s -w "%{http_code}" $purl)" == "200" ]];then
		echo 获取第$i版中...
		wget $purl -O ${pdate}-海外_split/RMRB${pdate}第$i版.pdf  > /dev/null 2>&1
	else
		break
	fi
i=$((10#$i + 1))
done

echo "合并中..."
pdftk ${pdate}-海外_split/*.pdf output 人民日报${pdate}_海外.pdf
echo $pdate人民日报国内、海外分版及合并版已下载完成！

```
	