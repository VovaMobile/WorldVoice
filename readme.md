# WorldVoice

In this highly interconnected and globalized era, language learning has become increasingly important. In language learning materials, native languages are often used to help explain foreign vocabulary and sentences, and multiple languages are often mixed together. In daily communication, we also often mix multiple languages and scripts. In books, newspapers, and online articles, multiple languages are often used to convey information, sometimes even within the same sentence, using Chinese and English or Chinese and Japanese.

The text composition, contextual meaning, and cross-lingual frequency of different digital content, such as language learning, mathematics, and literary works, may differ, and the corresponding speech reading method may also need to be adjusted accordingly to better meet the needs of different types of documents.

WorldVoice is a multi-language speech reading NVDA add-on, which supports five speech engines (VE, OneCore, Aisound, SAPI5, and RHVoice) and provides a variety of customization options. Users can adjust their settings for different contexts, maximizing the satisfaction of different user groups.

Its main features include:

*	Automatic switching between multiple languages
*	Individual speech parameter settings (speed, pitch, volume)
*	Multi-speech engine selection
*	Switching between numeric reading modes (digits and numerical values)
*	Customizable speech reading behavior (pause length for numbers, items, Chinese space, comma ignore between numbers)
*	Customizable text region.

## install

In addition to the general NVDA addon installation steps, if you want to use the VE and aisound voices, you need to install the core packages. If you want to use the VE and RHVoice voices, you need to install the voice packages.

Here are the steps to install the core packages:

*	Go to WorldVoice -> VE Core Installation, Aisound Core Installation, and import the corresponding core package zip files into the WorldVoice addon workspace.
*	If you are using the VE core, you also need to install the x86 version of [VC++ Redistributable Packages 2012](https://www.microsoft.com/en-US/download/details.aspx?id=30679) in your operating system (VSU_4\vcredist_x86.exe). If you have already installed the core and voice packages but still cannot load the WorldVoice synthesizer, try installing this component.

Here are the steps to install the voice packages:

*	If you want to use the RHVoice voice, please download the corresponding voice package addon from the official website. [Official download page](https://rhvoice.org/languages/).
*	If you want to use the VE voice, you can directly copy the regional folders (such as en, mnc, mnt, etc.) from the VE voice package addon and compress them into a zip file. Then, import it into the WorldVoice workspace through the "File Import" function in the WorldVoice interface. Since the addon form may be incompatible due to the NVDA version, causing the VE voice package to fail to load normally after updating NVDA, it is recommended to install the voice package in this file import method. Alternatively, you can use the VE addon voice package form, and download the corresponding voice package from the official website compatible with Vocalizer for NVDA. [Official download page](https://vocalizer-nvda.com/downloads).

## 設定

NVDA+ctrl+S 切換為 WorldVoice 語音合成器。

### 主要語音角色設定

透過 NVDA 設定: 語音(NVDA+ctrl+V) 設定基底語音角色與共通行為

*	語音速度、音調、音量設定
*	數字讀法：分為 2 個設定選項「數字語言」與「數字模式」，數字語言設定數字朗讀時使用的語音角色、數字模式分為數值與數字兩種
*	數字、項目、中文空白停頓參數可設定不同情境下的語音間停頓時長，數字愈小停頓愈短， 0 為不停頓。
*	忽略在數字間的逗號：選項勾選時會忽略數字中間的逗號，可讓數字位數的逗號標錯位置仍能正常朗讀數值。
*	啟用 WorldVoice 設定規則來偵測文字語言：當選項勾選時，會使用語音設定內的規則來偵測文字語言並切換語音朗讀。在部份情境此選項會與 NVDA 自動切換語言有相容性問題，建議兩者不要同時勾選。

### WorldVoice 語音設定（NVDA 功能表 -> WorldVoice -> 語音設定）

語音角色：可設定不同地區所使用的語音角色、各別語音角色速度、音調、音量、主要語音角色與地區語音角色一致性設定。

*	選擇地區後語音列表會列出該地區可用的語音角色，選擇後即完成該地區與語音角色的對應紀錄。
*	選擇語音角色後變聲列表會列出該語音角色可用的變聲，選擇後即完成該語音角色與變聲的對應紀錄。
*	當語音角色有選擇時，下方速度、音調、音量滑桿會變為該語音角色的設定值。
*	速度、音調、音量是依不同語音角色區分，每個語音角色有各自不同的速度數值，而非依地區區分。
*	保持主要語音引擎與地區語音引擎一致：將 NVDA 語音設定中的語音（主要語音）角色與 WorldVoice 語音設定中的地區對應語音（地區語音）引擎一致，當主要語音設定調整時，地區語音同步調整為相同的語音引擎。
*	保持主要語音角色與地區語音角色一致：將 NVDA 語音設定中的語音（主要語音）角色與 WorldVoice 語音設定中的地區對應語音（地區語音）角色一致，當主要語音或地區語音設定調整時，同步調整雙方的語音角色設定。
*	保持主要語音參數與地區語音參數一致：將 NVDA 語音設定中的語音（主要語音）與 WorldVoice 語音設定中的地區對應語音（地區語音）參數（速度、音調、音量）一致，當主要語音或地區語音設定調整時，同步調整雙方的語音參數設定。

語言設定：

*	用 unicode 編碼偵測文字語言勾選後，程式會根據讀到的字元偵測文字所屬地區。
*	偵測語言時忽略數字、偵測語言時忽略常見標點符號勾選後，數字與標點符號會判定為主要語音的地區文字。
*	增強語音命令：文字自動偵測語言、停頓語音指令的判斷與加入時間點是在 NVDA 的符號處理前或符號處理後進行。當選擇「符號處理後」項目時，可防止與其他使用到語音模組附加元件(ex: Instant Translate)的衝突。

語音引擎：可選擇要啟用的語音引擎，預設為 VE, OneCore, aisound

其他：

*	OneCore 提高語速：勾選後 OneCore 的語音角色速度會更快
*	VE 停頓參數：設定 VE 語音 session 開始與結束的停頓長度。（遇到句號或語音角色切換時皆會結束當前這條語音 session 並重啟一條新的語音 session）
*	數字點替代文字：設定數字中的小數點朗讀方式

### 其他設定：

WorldVoice -> Unicode 設定：可定義字元所隸屬的地區並依上下文或強制模式來判斷字元的地區，當「用 unicode 編碼偵測文字語言」勾選後自動偵測的判斷會加入此設定檔的規則，此功能可解決 NVDA 內部的 symbol 轉換規則造成在自動切換語言下不朗讀之問題。例如在某些情形下「.」不讀取時則可試著在規則中加入「.」的符號並選擇語言與模式來使其正確讀出。

WorldVoice -> 檔案匯入：可匯入檔案，可用於匯入語音包。

## 更新版本日誌

### v3.5

*	修正 aisound 音量回避 bug
*	修正 VE 遇 utf8 4bit 字元會讓後續文字不朗讀的問題
*	修正 VE 遇 unicode utf8 編碼錯誤時文字不朗讀的問題
*	在語音設定新增引擎分類，可選擇要啟用的語音引擎，預設為 VE, OneCore, aisound
*	相容於 NVDA 版本 2023.1

### v3.4

* 新增數字間停頓，提身數字內容聽讀判斷
* 新增項目間停頓功能，提身物件資訊聽讀判斷
* 修正 VE 數字模式為數值時會合併相鄰數字成為單一數值報讀
* 修正 OneCore 語速調整問題
* 修正 VE 開啟「游標移動時延遲讀出字元的字詞解釋」後遊標移動卡頓問題
* 修正 OneCore 與 RHVoice 「游標移動時延遲讀出字元的字詞解釋」無效的問題

### v3.3

* 支援 OneCore engine
* 地區與語音角色對應為 No Select 時使用主語音朗讀
* 修正符號轉中文報讀時會套用到中文空白停頓參數的問題
* 語音設定使用類別設定對話框，分為語音角色、語言切換、其他
* 在語音設定中的其他分類下加入 OneCore 加快語速開關
* 支援 RHVoice engine

### v3.2

*	修正在語音合成器非選擇 WorldVoice 時，語音設定問題，改以顯示提示文字
*	修正 aisound 音量調整問題
*	修正語音設定中偵測語言時間點的重啟條件
*	修正長按按鍵後語音無法中斷問題
*	修正多項語意問題(flake8)
*	相容於 NVDA 版本 2022.1

### v3.1

*	在網頁瀏覽中中斷無聲報讀
*	shift 可暫停/繼續語音報讀
*	按加減音量鍵不會中斷報讀
*	保持主要語音引擎與地區語音引擎一致功能
*	修正 VE 停頓的方式

### v3.0

*	支援 SAPI5 語音引擎
*	支援 Aisound 語音引擎
*	語音設定內新增語音角色切換時停頓長度
*	語音設定內新增 unicode 正規化方式選項
*	語音角色排序方式調整依語音引擎、語音角色名稱排序

### v2.2

*	語音設定內新增變聲選項，需依序設定地區、語音、變聲選項
*	修政偵測語言時間點選「符號處理前」後無法再變更之問題
*	新增阿拉伯語系翻譯

### v2.1

*	相容於 NVDA 版本 2019.3~ 2021.1
*	可套用 NVDA 不同組態設定
*	移除輸入手勢的多餘項目
*	速度內部數值換算百分比改非線性計算
*	設定選單調整將「在符號處理後偵測文字語言」更改為「偵測語言時間點」
*	偵測語言時間點：字元自動偵測語言時間點在 NVDA 的符號處理前或後進行。當選擇「符號處理後」項目時，可防止與其他使用到語音模組附加元件(ex: Instant Translate)的衝突
*	保持主要語音參數與地區語音參數一致：將 NVDA 語音設定中的語音（主要語音）與 WorldVoice 語音設定中的地區對應語音（地區語音）參數（速度、音調、音量）一致，當主要語音或地區語音設定調整時，同步調整雙方的語音參數設定
*	保持主要語音角色與地區語音角色一致：將 NVDA 語音設定中的語音（主要語音）角色與 WorldVoice 語音設定中的地區對應語音（地區語音）角色一致，當主要語音或地區語音設定調整時，同步調整雙方的語音角色設定

### v2.0

*	相容 NVDA 2021.1

### v1.7

*	小數點不讀修正(三數字間皆有小數點情形)
*	相容 NVDA 2021.1 以前的最後一版

### v1.6

*	修正數字模式下小數點不朗讀問題
*	更新 VE 核心包工作目錄，未來更新時可無需重新匯入
*	將「使用 WorldVoice 設定規則針測語言」的開關與「自動切換語言」的開關分開，避免部份情境兩者不相容問題。
*	修正啟用 unicode 自動語言針測時，預設語音與 NVDA 語言地區不相同但同語系時無法切換的問題
*	修正自動切換語言無勾選時 WorldVoice 變更語音語言命令被濾掉的問題

### v1.5

*	數字讀法分為 2 個設定選項「數字語言」與「數字模式」，將選項分為 2 維度以利選擇
*	忽略數字間逗點選項使數值報讀更正確
*	自動偵測語言功能當信任語音語言勾選時才使用不同解釋檔
*	語音設定中的值調整按確認才生效按取消會回到設定前的值
*	修正語音設定中當語音與預設語音相同時調整設定值後重啟 NVDA 後回到設定前的值
*	將自動語言切換設定與語音設定視窗合併
*	地區與語音對應加入 no-select 用來取消對應
*	支援快速鍵彈出語音設定與 Unicode 設定

### v1.4

*	修正檢視報讀內容開啟時無語音
*	音調內部數值換算百分比改非線性計算，讓預設值為 50
*	修正 unicode rule 強制模式下後方文字偵測錯誤
*	修正初始值類型錯誤導致語音設定對話框無法顯示
*	初始語音改優先使用預設語言之語音

### v1.3

*	加入 unicode 設定功能
*	修正單數字不會自動切換的問題
*	修正數字模式在特定場景下失效問題
*	移除 v1.2 的第1驅動
*	調整程式結構並預支援更多 TTS

### v1.2

*	提供第 2 驅動核心，整體相比第 1 驅動核心順暢，無偶爾速度不一致與小爆音問題
*	第 2 驅動功能比照第 1 驅動包括數字模式、中文空白間隔、忽略文件中的語言資訊等選項
*	第 2 驅動提供各語音速度、音調、音量各別調整，但與第 1 驅動對應數值不同，亦即第 1 驅動的速度 50 與 第 2 驅動的速度 50 不會有相同的語音速度
*	修正數字模式在選擇各數值語音下時間與小數點無正確朗讀的問題
*	修正無定義字元地區資訊時不朗讀的問題
*	修正數字模式在選擇各數字語音下無正確使用選擇的語音的問題
*	調整數字模式與忽略文件中的語言資訊處理順序，更符合預期朗讀邏輯

### v1.1

*	新增數字模式的選項，可選擇有安裝的語言朗讀數字並可分為數值與數字兩種。
*	新增忽略文件中的語言資訊的選項，此主要是避免自動切換語言勾選且原始文件就有提供語言資訊但不正確時(例如中文文字確標示英文語言)可能導致無法正確朗讀；或是在 word 數字會被標示成英文語言導致自動改用英文語音朗讀的狀況。
*	優化中文空白間隔，使中文物件與中文屬性間亦可停頓
*	加入其他中文語系的介面翻譯
*	略過從設定檔載入變聲功能，因目前 VE driver 底層的變聲功能無法正常使用且換語音時容易因設定值不符載入失敗導致要刪整個設定檔才能解決
*	合併 VE driver 3.1.2 的更新
*	其他細部優化
