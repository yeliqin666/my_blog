---
uuid: 2691a4f0-2a79-11ea-8486-776fa8141052
title: 电视直播
date: 2023-09-11 18:00:00
---

<link rel="stylesheet" href="//cdn.bootcdn.net/ajax/libs/video.js/7.6.0/video-js.min.css"><select id="selector" style="display:block;margin:10px auto"></select><video id="player" class="video-js vjs-big-play-centered vjs-16-9" autoplay controls preload="auto" data-setup="{}"><p class="vjs-no-js">To view this video please enable JavaScript, and consider upgrading to a web browser that <a href="//videojs.com/html5-video-support/" target="_blank">supports HTML5 video</a></p></video><script src="//cdn.bootcdn.net/ajax/libs/jquery/1.12.4/jquery.min.js"></script><script src="//cdn.bootcdn.net/ajax/libs/video.js/7.6.0/video.min.js"></script><script src="//cdn.bootcdn.net/ajax/libs/videojs-flash/2.2.0/videojs-flash.min.js"></script>
<script>var sources=[{name:"CCTV-1 综合",src:"https://dispatchnew.ulivetv.net/v/live/cgn2nfkwmp4w.m3u8?stream_id=cgn2nfkwmp4w&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
,{name:"CCTV-3 综艺",src:"https://node1.olelive.com:6443/live/CCTV3HD/hls.m3u8",type:"application/x-mpegURL"}
,{name:"CCTV-5 体育",src:"https://node1.olelive.com:6443/live/CCTV5HD/hls.m3u8",type:"application/x-mpegURL"}
,{name:"CCTV-6 电影",src:"http://cfss.cc/api/ysp/cctv6.m3u8",type:"application/x-mpegURL"}
,{name:"CCTV-7 国防军事",src:"https://dispatchnew.ulivetv.net/v/live/cgn1c6p2o2io.m3u8?stream_id=cgn1c6p2o2io&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
,{name:"CCTV-8 电视剧",src:"https://dispatchnew.ulivetv.net/v/live/cgn1g1rn5k8w.m3u8?stream_id=cgn1g1rn5k8w&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
,{name:"CCTV-9 纪录",src:"https://dispatchnew.ulivetv.net/v/live/cgn1jfvngjb4.m3u8?stream_id=cgn1jfvngjb4&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
,{name:"CCTV-10 科教",src:"https://dispatchnew.ulivetv.net/v/live/cgn1mnc500qo.m3u8?stream_id=cgn1mnc500qo&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
,{name:"CCTV-13 新闻",src:"https://live-play.cctvnews.cctv.com/cctv/merge_cctv13.m3u8",type:"application/x-mpegURL"}
,{name:"CCTV-14 少儿",src:"https://node1.olelive.com:6443/live/CCTV14HD/hls.m3u8",type:"application/x-mpegURL"}
,{name:"山东卫视",src:"​​​http://l1.weihai.tv:8081/hls/oK0gP1n8et.m3u8",type:"application/x-mpegURL"}
,{name:"湖南卫视",src:"​​​https://dispatchnew.ulivetv.net/v/live/cgwvl62c4og0.m3u8?stream_id=cgwvl62c4og0&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
,{name:"四川卫视",src:"​​​https://dispatchnew.ulivetv.net/v/live/cgwvu1zegukg.m3u8?stream_id=cgwvu1zegukg&token=c0vzuc7wqkzk",type:"application/x-mpegURL"}
];
$(function(){for(var o=videojs("player"),e=sources||[],n="<option>请选择电视频道</option>",c=0;c<e.length;c++)n+='<option value="'+c+'">'+e[c].name+"</option>";$("#selector").append(n).change(function(){o.src(e[+$("#selector").val()])})})</script>

