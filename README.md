[![GitHub release](https://img.shields.io/github/release/kanasimi/work_crawler.svg)](https://github.com/kanasimi/work_crawler/releases/latest/)[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fkanasimi%2Fwork_crawler.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fkanasimi%2Fwork_crawler?ref=badge_shield)

![GitHub Release Date](https://img.shields.io/github/release-date/kanasimi/work_crawler.svg)
![Github commits (since latest release)](https://img.shields.io/github/commits-since/kanasimi/work_crawler/latest.svg)
![GitHub commit activity the past week, 4 weeks, year](https://img.shields.io/github/commit-activity/y/kanasimi/work_crawler.svg)
[![Github All Releases Downloads](https://img.shields.io/github/downloads/kanasimi/work_crawler/total.svg)](https://github.com/kanasimi/work_crawler/releases)
[![Known Vulnerabilities](https://snyk.io/test/github/kanasimi/work_crawler/badge.svg?targetFile=package.json)](https://snyk.io/test/github/kanasimi/work_crawler?targetFile=package.json)
<!--
![Github Release Downloads](https://img.shields.io/github/downloads/kanasimi/work_crawler/v1.4/total.svg)
![Github Release Downloads](https://img.shields.io/github/downloads/kanasimi/work_crawler/latest/total.svg)
-->

# CeJS 線上小說漫畫下載工具 online novels / comics downloader
- [en] Download novels (→ epub) and comics with [GUI](https://en.wikipedia.org/wiki/Graphical_user_interface) and [command-line interface](https://en.wikipedia.org/wiki/Command-line_interface).
- [TW] 批量下載小說 (→ epub)、漫畫網站的工具。視窗+命令行介面。
- [CN] 批量下载小说 (→ epub)、漫画网站的网络爬虫。图形+命令行界面。
- [ja] ウェブ小説 (→ epub)、ウェブ漫画作品を一括ダウンロードツール。グラフィカル+コマンドラインインターフェース。

## TOC 快速瀏覽
* [Installation 安裝](#installation-安裝)
   * [Lazy installation 懶人安裝法](#lazy-installation-懶人安裝法)
* [Execution 執行](#execution-執行)

## Features 特點
* 可自動下載小說封面以及章節中的插圖。
* 本工具會盡量取得原有的圖片檔案中最高品質的，並自動檢核下載的圖片是否是否完整。若有破損將重新下載。
* 跨平臺支援：支援 Windows, Linux, Mac。
* 採用 CeJS [線上作品爬蟲程式庫](https://github.com/kanasimi/CeJS/blob/master/application/net/work_crawler.js)來製作 crawler，可自行配置與設定。
* 對於漫畫，下載完畢後可以章節為單位自動產生壓縮檔，並自動刪除下載目錄原始圖檔/清除暫存檔。每次下載前將自動讀取壓縮檔資料，僅更新有問題的圖檔。（請注意：必須先安裝 7-Zip **18.01 以上的版本**）

## OS support 作業系統支援
| Platform 作業系統平臺 | support 支援狀況 |
| --- | --- |
| Windows | ✔️ |
| macOS | ✔️ |
| UNIX, Linux | ✔️ |

## Supported sites 已完成之網站工具
* For novels, please install [7-Zip](https://en.wikipedia.org/wiki/7-Zip) command-line version first. 請注意：必須先安裝 7-Zip **18.01 以上的版本**，這樣才能製作 .epub 小說電子書、壓縮漫畫章節。
* 各線上作品網站往往不時改版（更改結構），同時造成本工具無法正常作動；因此若有無法正常運作的情況請見諒，這通常得要更改原始碼方能回復正常。

已撰寫完的各大小說漫畫網站工具包括：

### Japanese web fictions / Japanese light novels ライトノベル 日本輕小說 日本語のオンライン小説
[novel.ja-JP/](novel.ja-JP/)*.js, web pages → epub

| Site 平臺名稱 | Tool file | Note 說明 |
| --- | --- | --- |
| [アルファポリスの小説](https://www.alphapolis.co.jp/novel) | AlphaPolis.js | レンタルする話は取得できません |
| [カクヨム](https://kakuyomu.jp/) | kakuyomu.js | |
| [ハーメルン](https://syosetu.org/) | Hameln.js | |
| [小説を読もう！](https://yomou.syosetu.com/) | yomou.js | [小説家になろう](http://syosetu.com/) |
| [ノクターンノベルズ](https://noc.syosetu.com/) | noc.js | [小説家になろう](http://syosetu.com/)の[男性読者向けの18禁部門サイト](http://noc.syosetu.com/site/faq/) |

### Chinese web fictions / novels 中国内地小说 中国のオンライン小説
[novel.cmn-Hans-CN/](novel.cmn-Hans-CN/)*.js, web pages → epub

| Site 平臺名稱 | Tool file | Note 說明 |
| --- | --- | --- |
| [起点中文网](https://www.qidian.com/) | qidian.js | **本工具無法下載 VIP章节內容** |
| [八一中文网](http://www.81xsw.com/) | 81xsw.js | [PTCMS](https://www.ptcms.com/)系统 |
| [八八读书网](http://www.88dus.com/) | 88dus.js | 88读书网(88dushu)，PTCMS? |
| [顶点小说](http://www.23us.com/) | ~~archive/23us.com.js~~ | PTCMS，限制了取得頁面的數量和頻率，暫時放棄。 |
| [顶点小说](https://www.23us.cc/) | 23us.js | [WMCMS](http://www.weimengcms.com/index.html) (未梦开源小说程序) [仿电脑顶点小说模板](http://www.weimengcms.com/html/temple/article/141.html) or PTCMS? |
| [恋上你看书网](http://www.630book.la/) | 630book.js | |
| [飘天文学](http://www.piaotian.com/) | piaotian.js | NOT PTCMS |
| [落霞小说网](http://www.luoxia.com/) | luoxia.js | WordPress，數量少、速度較慢但品質較高，較少錯字和自我審查。 |
| [努努书坊](https://www.kanunu8.com/) | kanunu.js | 有些非流行網路小說的書。 |
| [稻草人书屋](http://www.daocaorenshuwu.com/) | daocaoren.js | 有些非流行網路小說的書 |
| [卡提諾論壇 小說頻道](https://ck101.com/forum.php?gid=1180) | ck101.js | Discuz! X3 |

* 中國大陸之小說文字常常會被[審查](https://zh.wikipedia.org/wiki/%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E8%A8%80%E8%AE%BA%E5%AE%A1%E6%9F%A5)而消失、變造。例如黑名單關鍵字轉為拉丁字母或是[打星號](https://ck101.com/thread-3500214-1-1.html)，以及數字 0 改成 o、9 改成 q 等等。有時需要多下載幾個網站的文件再做比較。

### Chinese webcomics 中国内地漫画 中国のウェブコミック
[comic.cmn-Hans-CN/](comic.cmn-Hans-CN/)*.js, images → zip
* 本工具無法下載需VIP付費、已屏蔽或刪除的內容。

| Site 平臺名稱 | Tool file | Note 說明 |
| --- | --- | --- |
| [腾讯漫画](http://ac.qq.com/) | qq.js | **本工具無法下載VIP付費內容** 2017/8/15 起取消了今日限免 |
| [网易漫画](https://manhua.163.com/) | 163.js | 2017/7/13 **本工具無法下載VIP付費內容** |
| [有妖气](http://www.u17.com/) | u17.js | **本工具無法下載VIP付費內容** |
| [知音漫客](https://www.zymk.cn/) | zymk.js | |
| [大角虫漫画](https://www.dajiaochongmanhua.com/) | dajiaochong.js | 2018/6/12 開始永久付費制。 |
| [动漫屋网](http://www.dm5.com/) | dm5.js | 似乎不能並行下載圖片，下載速度較慢。似乎拿來下載日本漫畫的人比較多。 |
| [土豪漫画](https://www.tohomh.com/) | tohomh.js | 系統似 dm5。 |
| [快看漫画](https://www.kuaikanmanhua.com/) | kuaikan.js | |
| [微博动漫](http://manhua.weibo.com/) | weibo.js | **本工具無法下載VIP付費內容**<br />竟然所有資料皆可由API取得，實在是程序猿的好搭檔！ |
| [漫画台](http://www.manhuatai.com/) | manhuatai.js | |
| [大古漫画网](https://www.dagumanhua.com/) | dagu.js | 2018/10/19–11/24 間，[9妹漫画网](http://www.9mdm.com/)改名大古漫画网。 |
| [360漫画](http://www.xatxwh.com/) | 360taofu.js | 有些漫畫畫質較高，然而本站有太多缺圖。採用[晴天新漫画系统](http://www.qingtiancms.com/manhua/)[模板1](http://manhua2.qingtiancms.net/) |
| [乙女漫画](http://www.nokiacn.net/) | nokiacn.js | 日本漫畫較多。採用[晴天新漫画系统](http://www.qingtiancms.com/manhua/)[模板2](http://manhua3.qingtiancms.net/) |
| [看漫画](https://www.manhuagui.com/) | manhuagui.js | **漫画柜**原[爱看漫](http://www.ikanman.com/)。採用[圣樱漫画管理系统](http://cms.shenl.com/sinmh/) MHD模板?<!-- <br />[晴天漫画系统](http://manhua.qingtiancms.com/)改? --> |
| [古风漫画网](http://www.gufengmh.com/) | gufengmh.js | 採用[圣樱漫画管理系统](http://cms.shenl.com/sinmh/) MHD模板 |
| [36漫画网](https://www.36mh.com/) | 36mh.js | 採用[圣樱漫画管理系统](http://cms.shenl.com/sinmh/) MHD模板 |
| [动漫之家](https://www.dmzj.com/) | dmzj.js | 僅處理漫畫。有時會無法讀取。採用[圣樱漫画管理系统](http://cms.shenl.com/sinmh/) DMZJ模板 |
| [733漫画网](http://www.733mh.net/) | 733mh.js | 有時會無法讀取。733mh與733dm內容類似...<br />可能為早期[晴天漫画系统](http://manhua.qingtiancms.com/)？[晴天新漫画系统](http://www.qingtiancms.com/manhua/)[模板3](http://manhua4.qingtiancms.net/)?? |
| [733动漫网](https://www.733dm.net/) | 733dm.js | 僅處理漫畫。2018/11/9 之後 (11/16之後?) 改版成 晴天漫画系统 |
| [卡推漫画](http://www.katui.net/) | katui.js | 系統同 archive/733dm.201808.js，可能為早期[晴天漫画系统](http://manhua.qingtiancms.com/)？ |
| [扑飞漫画](http://www.pufei.net/) | pufei.js | 系統同 archive/733dm.201808.js，可能為早期[晴天漫画系统](http://manhua.qingtiancms.com/)？ |
| [塔多漫画](http://www.taduo.net/) | taduo.js | 系統同 archive/733dm.201808.js，可能為早期[晴天漫画系统](http://manhua.qingtiancms.com/)？ |
| [漫画DB](http://www.manhuadb.com/) | manhuadb.js | 以臺灣翻譯日本的漫畫單行本為主 |
| [漫画160](http://www.mh160.com/) | mh160.js | 與 733mh.js 相同系統 |
| [哦漫画](http://www.omanhua.net/) | omanhua.js | |
| [汗汗酷漫](http://www.hhimm.com/) | hhcool.js | 2018/4/27 最後一次存取域名 http://www.hhcool.com/ |
| [comico](http://www.comico.com.tw/) | comico.js | 本工具經設定帳號資訊後，可自動使用閱讀卷(レンタル券)，但無法處理互動式漫畫、coin收費作業。 |
| [WEBTOON](https://www.webtoons.com/zh-hant/) | webtoon.js | NAVER WEBTOON 中文官網 韓國漫畫<br />本工具無法下載有動態效果的漫畫。 |
| [咚漫中文官网](https://www.dongmanmanhua.cn/) | dongman.js | NAVER WEBTOON 中文官网 韩国漫画<br />本工具無法下載有動態效果的漫畫。 |
| ~~[热漫吧](http://www.remanba.com/)~~ | ~~archive/remanba.js~~ | 自 2016/12/27 14:42 最後一次成功連接後，下午起就持續 404 至 2018/6/11 未復原。 |
| ~~[三七阅读](http://www.37yue.com/)~~ | ~~archive/37yue.js~~ | 自 2017/6/9 下午最後一次連接後，2017/6/10 9時起就持續 404 至 2018/6/11 未復原。 |
| ~~[爱漫画](http://www.2manhua.com/)~~ | ~~archive/2manhua.js~~ | 許多作品似乎從2017/9/3起就沒有更新。2017/5/16 4:43 最後一次成功連接，至 2018/6/11 未復原。 |

### Japanese webcomics 日語網路漫畫 日本語のウェブコミック
[comic.ja-JP/](comic.ja-JP/)*.js, images → zip

| Site | Tool file | Note |
| --- | --- | --- |
| [ComicWalker](https://comic-walker.com/) | ComicWalker.js | KADOKAWAの無料漫画（マンガ） コミックウォーカー |
| [ヤングエースUP](https://web-ace.jp/youngaceup/) | youngaceup.js | KADOKAWA webエース |
| [アルファポリスの公式Web漫画](https://www.alphapolis.co.jp/manga/official) | AlphaPolis_manga.js | レンタルする話は取得できません |
| [モアイ](http://www.moae.jp/) | moae.js | 講談社 モーニング・アフタヌーン・イブニング合同Webコミックサイト |
| [pixivコミック](https://comic.pixiv.net/) | pixivcomic.js | pixivコミック(ぴくしぶこみっく) |
| [OVERLAP](https://over-lap.co.jp/gardo/) | OVERLAP.js | オーバーラップ コミックガルド: [ActiBook](https://ebook.digitalink.ne.jp/)系統 |
| [MAGCOMI](https://comic.mag-garden.co.jp/) | MAGCOMI.js | マグコミ: [ActiBook](https://ebook.digitalink.ne.jp/)系統 |
| [コミコ](https://www.comico.jp/)<br />[オトナ限定 コミコ](http://plus.comico.jp/) | comico_jp.js<br />comico_jp_plus.js | 本工具經設定帳號資訊後，可自動使用閱讀卷(レンタル券)，但無法處理互動式漫畫、coin收費作業。 |
| [XOY](https://xoy.webtoons.com/) | XOY.js | NAVER WEBTOON ja<br />2018.09.13: [XOYの作品が「LINEマンガ」に移行されます。](https://xoy.webtoons.com/ja/notice/detail?noticeNo=849) |

### English webcomics 英語網路漫畫 英語のウェブコミック
[comic.en-US/](comic.en-US/)*.js, images → zip

| Site | Tool file | Note |
| --- | --- | --- |
| [Manga Mew](https://www1.mangamew.com/) | mangamew.js | 一些圖片在檔案最後會多加個字元 0A，因此被判別為非正規圖片檔。 |
| [Manga New](http://manganew.net/) | manganew.js | Using Microsoft IIS? |
| [Rocaca](http://www.rocaca.com/) | rocaca.js | 受到 Cloudflare 保護 |
| [WEBTOON](https://www.webtoons.com/en/) | webtoon.js | NAVER LINE WEBTOON |

## Installation 安裝

若是想要使用系統安裝的方法，您可以 **[直接下載安裝包![GitHub release](https://img.shields.io/github/release/kanasimi/work_crawler.svg)](https://github.com/kanasimi/work_crawler/releases/latest/)**，惟 **安裝包不含最新的功能**，有些網站下載起來會出問題。安裝包現在落後最新測試版修正次數：![Github commits (since latest release)](https://img.shields.io/github/commits-since/kanasimi/work_crawler/latest.svg)。若是欲採用最新的版本，或者用作研究開發、想要使用命令行介面作批次處理，請採用下列步驟。

### Lazy installation 懶人安裝法
為了想趕快嘗鮮的您～<!-- （已經做過的步驟可以跳過） -->
1. 先安裝 [Node.js](https://nodejs.org/) 與 [7-Zip](https://www.7-zip.org/) 18.01 以上的版本。<!-- 下載小說須先安裝 [7-Zip](https://en.wikipedia.org/wiki/7-Zip) 以製作 .epub 電子書。 -->（已經安裝過的可以跳過）
2. 下載並儲存本工具安裝檔 <code>[work_crawler.updater.js](https://raw.githubusercontent.com/kanasimi/work_crawler/master/work_crawler.updater.js)</code>（按右鍵另存新檔）。本工具安裝檔 **預設會將所有組件放在 <code>work_crawler-master</code> 目錄下**。
3. <details><summary>在命令行介面下執行安裝檔 <code>work_crawler.updater.js</code>。（點擊本行可獲得更詳細的說明）</summary>

   1. **進入[命令行介面](https://zh.wikipedia.org/wiki/%E5%91%BD%E4%BB%A4%E8%A1%8C%E7%95%8C%E9%9D%A2)下**：
      * Windows 10 下，請按下<kbd>[⊞ Windows鍵](https://zh.wikipedia.org/wiki/Windows%E9%94%AE)</kbd> + <kbd>X</kbd> → 選擇 **命令提示字元**。（如下圖的示範）
      * Windows 7 下[打開命令行介面](https://carolhsu.gitbooks.io/django-girls-tutorial-traditional-chiness/content/intro_to_command_line/README.html)，請從  開始 → 所有程式 → 附屬應用程式 → 選擇 **命令提示字元**

      ![Windows 10 下，進入命令行介面](https://lh3.googleusercontent.com/yFKRG6LTfvbJhMljgIXrEUFivGl4LRYgs0FlNBCBZ1KmwUW2paSoubLhyWGhS7S9GsHe1ef7Bt3TRyf5IHWRLdFL_SqywkPikecwlSpYtPHM6KRlyEaFWsWZqrS7DF3JzzcycnfxfQ=w2400)

   2. **進到本工具安裝檔 <code>work_crawler.updater.js</code> 所在的目錄**：
      * 若是您視窗的 **背景為藍色**，表示您使用的可能是 [PowerShell](https://zh.wikipedia.org/wiki/Windows_PowerShell)，您應該使用這種形式的指令來切換目錄：<code style="color:#888;background-color:#008b8b;">cd "本工具安裝檔所在的目錄"</code>。
      * 若是您視窗的 **背景為黑色**，表示您使用的可能是 [命令行介面](https://zh.wikipedia.org/wiki/%E5%91%BD%E4%BB%A4%E8%A1%8C%E7%95%8C%E9%9D%A2)，您應該使用這種形式的指令來切換目錄：<code>cd/d "本工具安裝檔所在的目錄"</code>（**cd/d** 表示「同時變更工作磁碟機及其工作目錄」的意思）。

   3. **執行命令以下載最新版本組件**：
      ``` sh
      node work_crawler.updater.js
      ```
</details>

4. 然後就能[開始試用](#execution-執行)囉。若是您希望使用[圖形使用者介面](https://zh.wikipedia.org/wiki/%E5%9B%BE%E5%BD%A2%E7%94%A8%E6%88%B7%E7%95%8C%E9%9D%A2)，請執行 <code>work_crawler-master</code> 目錄下面的 <code>start_gui_electron.bat</code> 或 <code>start_gui_electron.sh</code>。
   <details><summary>下載 CeJS 程式庫後本工具安裝的目錄看起來的樣子：</summary>

   ![下載 CeJS 程式庫後本工具安裝的目錄看起來的樣子](https://lh3.googleusercontent.com/rVTuL3GHoWjXcJBW3O0KutvRTlf-HjQa5dzm_PJwizhMDN38JG8RIdJ7nuZyWA6m2G9d2McEP_XdyNmGwn0kVdSjwDzJaS6w9D9SOtETBCnO9fAue82-J3qMtEm8yxgkjOLr5EBnjg=w150-h330-no)

   以下是在linux下直接操作上述作業時的指令，Windows用戶可以跳過，直接[開始試用](#execution-執行)。
   ``` sh
   # sample commands to extract work_crawler + cejs
   curl -O https://raw.githubusercontent.com/kanasimi/work_crawler/master/work_crawler.updater.js
   # wget https://raw.githubusercontent.com/kanasimi/work_crawler/master/work_crawler.updater.js
   node work_crawler.updater.js
   ```
</details>

5. 若是您將 CeJS 放置在其他目錄底下，您可以從 <code>[_repository_path_list.txt](https://github.com/kanasimi/CeJS/blob/master/_for%20include/_repository_path_list.sample.txt)</code> 這個檔案來設定放置的路徑。
6. 您可設定 <code>work_crawler_loder.configuration.js</code> 以指定下載的作品檔案要放到哪個目錄底下。 (see [work_crawler_loder.js](https://github.com/kanasimi/work_crawler/blob/master/work_crawler_loder.js))
7. 每次要更新到最新版本時，只要進到工具安裝檔所在目錄，重新執行一次本工具安裝檔即可。
   ``` sh
   node work_crawler.updater.js
   ```
   由於本工具會 cache 作品資訊，更新幅度較大的時候，新程式可能無法讀取這些舊格式的 cache，會產生錯誤；此時您需要刪除下載目錄中所有的 cache，重新下載作品。例如 search.json, servers.json 以及作品目錄下面，以作品名稱為名的 .json 檔案。

<!-- use npm:
3. 在命令行介面下，進到解壓縮後工具檔所在的目錄，執行命令以下載 CeJS 程式庫：（`npm install` 可能將 cejs 安裝在此目錄下之 node_modules/cejs 目錄內 ）
   ``` sh
   npm install cejs
   ```
4. 然後就能[開始試用](#execution-執行)囉。
* 請注意：採用 <code>npm install cejs</code> 安裝的可能不是最新版的 CeJS，尚未加入最新功能。當採用新版下載工具與舊版 CeJS 程式庫時，執行起來會出錯，請見諒。**建議採用下方一般正常安裝方法**，下載最新版本 [CeJS](https://github.com/kanasimi/CeJS) 壓縮檔，解開後配置；而不是直接執行 <code>npm install</code> 安裝舊版的程式庫。
-->

### Normal installation 一般正常安裝方法
1. Please see [Node.js usage section at CeJS](https://github.com/kanasimi/CeJS#nodejs-usage) for detail.
2. Setup [_repository_path_list.txt](https://github.com/kanasimi/CeJS/blob/master/_for%20include/_repository_path_list.sample.txt) if necessary.
3. Setup <code>work_crawler_loder.configuration.js</code> (see [work_crawler_loder.js](https://github.com/kanasimi/work_crawler/blob/master/work_crawler_loder.js)). 最後設定好設定檔 <code>work_crawler_loder.configuration.js</code>。例如指定 <code>global.data_directory</code>。

#### Setup GUI 設定視窗型態介面
若是您在作研究開發時，希望使用[圖形使用者介面](https://zh.wikipedia.org/wiki/%E5%9B%BE%E5%BD%A2%E7%94%A8%E6%88%B7%E7%95%8C%E9%9D%A2)，那麼您還需要安裝 [Electron](https://electronjs.org/)。若是您採用懶人安裝法，應該已經安裝過 Electron，可以直接採用圖形使用者介面。
1. 請在[命令行介面](https://zh.wikipedia.org/wiki/%E5%91%BD%E4%BB%A4%E8%A1%8C%E7%95%8C%E9%9D%A2)下，進到本工具安裝的目錄，執行命令以安裝 Electron 程式庫：
   ``` sh
   npm i -D electron@latest
   ```
2. 在本工具安裝的目錄下，執行 <code>start_gui_electron.sh</code> 或 <code>start_gui_electron.bat</code>。

   ![視窗型態介面](https://lh3.googleusercontent.com/3dGaOZnsMNrCr6OrYdSg_Ia6dgQBZHBbwplgbOAaQn4RQkLcxGJbly3IDRicw6PbZFwG97TfJuHl3EeAqc3Nl34Tc6LmntqrxwCZl6djLfOqfZnnlo_6aCwUGS0rraGf8xBTd8JEYg=w852-h896-no)

## Execution 執行
所有操作都必須進到工具檔所在的目錄，在命令行介面下執行。
1. 確認要下載的網站名與作品名。之後在命令行介面下，執行：（請在作品的名稱外面加上引號）

   ``` sh
   node 工具檔名.js "作品名" [option=true] [option=value]
   node 工具檔名.js "l=作品列表檔案名" [option=true] [option=value]
   ```

   e.g.,
   ``` sh
   cd comic.cmn-Hans-CN && node qq.js "狐妖小红娘" skip_error=true
   cd novel.cmn-Hans-CN && node qidian free && echo 下载 起点中文网限免作品
   cd novel.cmn-Hans-CN && node 23us "斗罗大陆Ⅲ龙王传说" proxy=localhost:8080
   cd comic.cmn-Hans-CN && node 2manhua "大主宰" recheck=true
   cd comic.cmn-Hans-CN && node ikanman "l=ikanman.txt" recheck=true
   cd novel.cmn-Hans-CN && echo "via id" && node 630book "267"
   cd novel.ja-JP       && node yomou "転生したらスライムだった件"
   ```

   ![命令行介面下執行命令](https://lh3.googleusercontent.com/r1-jB1Cmaznb5kseN97xUQyGzrsJJgek25Ifyvey8scMm311WjnjIAy-FpmiTtIVupyimDTWrVL7aI2cI7i2FRllR_QWMiLsRgF-kzDJnYMRaTRMVXrG2XkfEhHPh5Qvns0XQjROcw=w2400)

2. 下載的檔案將放在設定檔 <code>work_crawler_loder.configuration.js</code> 的 <code>global.data_directory</code> 所設定的目錄下。若採[懶人安裝法](#lazy-installation-懶人安裝法)，則預設放在解壓縮後工具檔所在的目錄下。
3. 本工具會循序下載每個章節，對於漫畫基本上每個章節的圖片會並行下載。不可並行下載同一個網站的同一個作品，否則會出現衝突。若是想要並行下載不同網站或是不同的作品，那麼您就需要再開一個命令行介面來執行工具檔。
4. 若是下載出錯，**重新執行即可接續下載**。

## Workflow 工作流程
* 本工具將把所指定的漫畫下載至特定目錄中（預設為工具檔名，如 <code>manhuatai</code>），每套漫畫一個目錄。

   ![folder](https://lh3.googleusercontent.com/-Gu8klHdiKfm9c3IKkYLVLd26Wc5W2Fz2QX7--7QNgjewXZRoRDf3uCNxTqRqmYfdzZxly7BRFPhdYWE2bZXKweer_QaC5T2Wxv5fVGuVC2vGxMtG2szUqFgHKx7n9uMaRKCOfWU7A=w589-h386-no)

   ![folder inside work](https://lh3.googleusercontent.com/qEzhnefvmuTdt1o3jR68uhJOkkGafSPiov1QwfuMyDp2AJesQ6sSpBQnUdT_T5-3qbb-u_R48gm_biNWvNT8NNIb-UtvbsUnF02_ADoTXdy-YjhlFCWr4QYigeZ0fGBmv7swnb8GXA=w225-h343-no)

   ![folder inside chapter](https://lh3.googleusercontent.com/DsQ4d1Px6WXJWrARFQhnVz5DfCAYkJleDsbeku4LVSJjJuvHjAncDccoqq9ML45KtLgkmOzjhJlaUYyy7C6Sg2KwMRx56yxK1fp9wJTJlAciH8ybkYLcSz05LtbJyrHxv50PZIsrSg=w333-h265-no)

* 接續下載時，將從上次的進度（最後下載的章節）接著下載。

   ![接續下載](https://lh3.googleusercontent.com/PpNidzWOTdQe0VMxIfgXrCJVVJ_g5dXENCPMM7OMX7vdlTywcCqN5fKtTxNT8Fm9hTG3-2H5mdHfgFPDpHzP2yeSRQ8ObuabMGnFnatDId5UvSXC9BOk_94O2CxCAkSLTov6KU-qSA=w732-h463-no)

* 若是下載小說，最後將包裝成可匯入 calibre 的 epub。

   ![小說 → epub list](https://lh3.googleusercontent.com/fYB5zhGgw8Thh5mGzR_5PVSCWDqWxOUHxQRaiqDOx0VS0BdsIlNMNCkxvjl1RpNWI5IBfYMZ_LgHTkiuFZvDPOqMRa-6JHsTN3Od3LgD4DPMDy6Lk4ccbZlTB-w4cLjYweEExYJehg=w1366-h738-no)

   ![小說 → epub](https://lh3.googleusercontent.com/JJ4SGDQF-HzQb0baRZ0mCio19jJTnNp3VnWutirYgZbYg5i--ufS_ElL8DEetP6x7uJ4HUv8szNqzVLbGlr84_OnxFxjIZCDsOEOEmKBubYC6PkpaE2xBYk9KIHzBR4YPwjQVM2FTA=w1366-h738-no)

## Uninstallation 移除
* 若是您採用安裝包，請利用系統正規的移除方法或移除介面。否則要移除本工具，只需先備份好之前下載過的漫畫，之後將解壓縮後工具檔所在的目錄整個刪除即可。
* 作品下載的標的目錄（存放圖片檔與紀錄檔的目錄）需另外手動刪除。

## FAQ 常見問題集
<details><summary>如何從某個章節開始下載</summary>

* 若是使用命令列介面，您可以採用 start_chapter 這個參數與 recheck 參數，就可以挑選開始下載的章節。

   範例指令:
   ``node qq 作品名 start_chapter=20 recheck``

* 圖形介面在右手邊的 **下載選項** 應該可以看到有一個 **start_chapter: 將開始/接續下載的章節編號。必須要配合 .recheck。 (number)**。

   請輸入章節的數字，之後指定 start_chapter 上面的 recheck，點擊開始下載就可以接續下載了。
</details>

<details><summary>下載圖片或電子書的資料夾內，有些不是圖片或電子書的檔案</summary>

* 這些json檔是用來記錄程式執行的狀態。可以刪除，但若常常接續下載，可能會受影響。例如必須重新搜尋作品、重新檢查下載狀況等等。
</details>

<details><summary>掃毒軟體報錯！</summary>

* 應該是因為使用的 CeJS 函式庫包山包海，裡面用到一些專門用於檔案操作的函數、FileSystemObject 物件、WScript 物件，所以掃毒軟體以為有問題。這個程式天天都在測試，漫畫小說下載並不會用到這些功能，您大可放心。
</details>

<details><summary>作品目錄下可否放置無關的檔案</summary>

* 作品目錄下可以放置無關的檔案，不會影響到本工具運行。
</details>

## Notes 附注
* 目前本工具不支援 GUI 安裝包自動更新。
* 對於本工具已經包含的下載模式，熟練後一般約需2至4小時新增或更新下載工具，以達初步可用狀態。
* 小說作品採用單線程下載，以避免對網站造成過度的負荷。漫畫作品則以章節為單位多線程下載，每個章節的圖片下載完畢之後，再接著下一個章節。
* 若可能，[您應該檢核並參與維護您需要的軟體](https://gist.github.com/dominictarr/9fd9c1024c94592bc7268d36b8d83b3a)。現在您可以參與本工具開發了！本工具歡迎熱心友人參與開發，以改進這個工具。

## Purpose 公開目的
* 示範如何使用 [CeJS](https://github.com/kanasimi/CeJS) 之 [線上作品爬蟲程式庫 (module)](https://github.com/kanasimi/CeJS/blob/master/application/net/work_crawler.js) 批量下載各線上小說漫畫網站。
* 展示程式撰寫當時，各線上小說漫畫網站之網站資料結構。
* 提供離線瀏覽小說漫畫功能，以利個人化閱覽方式。增進閱覽體驗、掌控閱覽環境。
* 增加對閱讀權的掌控能力，預防暫時無法連接網頁，或者數十年後找不到記憶中閱覽過的作品。

非常歡迎[提供使用意見與改善建議](https://github.com/kanasimi/work_crawler/issues/new)。

## Announce 聲明
* 本工具僅供同好學習和研究，嚴禁傳播或用於任何商業、非法用途！請小心利用本工具。所下載或備分之內容版權屬原作者所有，請勿公開散布傳播。利用本工具可能引起的任何糾紛或損失損害，本人恕不負責。

<!--
TODO:
auto-update

https://ctrlq.org/google/photos/
-->


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fkanasimi%2Fwork_crawler.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fkanasimi%2Fwork_crawler?ref=badge_large)