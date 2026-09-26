// ==UserScript==
// @name               B站解锁8K杜比全景声HDR
// @version            1.0
// @description        B站解锁8K杜比全景声HDR
// @match              *://www.bilibili.com/blackboard/html5playerhelp*
// @match              *://www.bilibili.com/video*
// @match              *://www.bilibili.com/list*
// @match              *://www.bilibili.com/blackboard*
// @match              *://www.bilibili.com/watchlater*
// @match              *://www.bilibili.com/bangumi*
// @match              *://www.bilibili.com/watchroom*
// @match              *://www.bilibili.com/medialist*
// @match              *://bangumi.bilibili.com*
// @match              *://live.bilibili.com/*
// @run-at             document-start
// @grant              none
// ==/UserScript==

(function(){'use strict';try{localStorage.setItem('bilibili_player_force_DolbyAtmos&8K&HDR','1');localStorage.setItem('bilibili_player_force_hdr','1')}catch(e){}const rawGetItem=Storage.prototype.getItem;Storage.prototype.getItem=function(key){if(key==='enableHEVCError'){return undefined}return rawGetItem.apply(this,arguments)};const fakeUA='Mozilla/5.0 (Macintosh; Intel Mac OS X 15_7_2) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/26.0 Safari/605.1.15';try{Object.defineProperty(navigator,'userAgent',{get:()=>fakeUA,configurable:true});Object.defineProperty(navigator,'platform',{get:()=>'MacIntel',configurable:true});Object.defineProperty(navigator,'vendor',{get:()=>'Apple Computer, Inc.',configurable:true})}catch(e){}})();