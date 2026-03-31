```markdown
 AI生圖入門：從購物清單到設計畫面

> 本教程基於 DiT 模型，示範均以 tsubaki.2 為準

很多人用 AI 畫圖時，會遇到一個共同的困惑：明明寫了很多詞，但出來的圖總是差一點——要嘛很平、要嘛很怪、要嘛沒有重點。

這通常不是模型不夠強，而是我們在用 AI 對話的方式上，出了一點偏差。

這份教程會用最簡單的方式，幫你建立一種新的思考方式。我們只專注兩件事：

1. 怎麼想：設計畫面，而不是列購物單
2. 怎麼做：用 Prompt 和簡單工具來實現你的設計


```
## 第一部分：核心觀念——AI 不是畫家，是猜圖高手

首先，我們要建立一個最重要的理解：

> AI 畫圖，不是像人類畫家一樣，一筆一筆畫出來的。它更像一個**猜圖高手**，根據你給的提示詞，一步步猜出一張最合理的圖。

- 如果你說得模糊，它就只能亂猜，結果可能千奇百怪
- 如果你說得精確，它就能猜到你想的那張圖

這就是為什麼我們要從列清單轉變為設計畫面。

---
## 第二部分：你的 Prompt 是購物清單還是視覺設計？

大多數人寫 Prompt，是這樣的：

```text
a girl, long hair, skirt, night, rain, city
```

這在 SD 1.5 或 SDXL 上沒有問題，但如果是 DiT 模型——你只是在羅列一些不相干的東西。

在 DiT 模型（Tsubaki / Tsubaki.2）上，你應該告訴 AI 它們應該長什麼樣、放在哪裡。AI 拿到這份清單，只能從零開始畫畫。

一份好的 Prompt，應該遵循結構優先的原則

先定骨架，再填血肉。正確的順序是：

構圖 → 光線 → 景深 → 視角 → 主體 → 環境 → 細節

來看一個實際的例子：

```text
asymmetrical composition, subject on left third, soft side lighting, shallow depth of field with focus on eyes, low angle view, 1girl with long black hair and red dress, standing in a rainy city street, glowing neon reflections on wet pavement
```

差別在哪？

寫法 特點 結果
SD / SDXL 式 先列主體和環境，沒有空間感 AI 亂猜，結果不穩定
設計圖式 先定構圖、光線、景深，再說畫面怎麼擺 AI 照著結構框架填內容，結果可控

為什麼順序這麼重要？

因為 AI 畫畫的生成過程是從整體到局部：

· 前 20% 的 prompt：決定構圖、光線、景深——這些是畫面的骨架
· 後 80% 的 prompt：填充主體、環境、細節——這些是畫面的血肉

骨架歪了，血肉再精緻也沒用。這就是為什麼要把結構性描述放在最前面。

---
## 第三部分：設計畫面的七個步驟

要切換到視覺設計師的思維，你只需要在寫 Prompt 前，按順序問自己七個問題。這七個問題，決定了你畫面的基礎結構。

1. 構圖：畫面怎麼擺？

構圖方式 英文提示詞 適用場景
中心構圖 central composition 穩定、莊重
三分構圖 rule of thirds 自然、平衡
對角線構圖 diagonal composition 動感、張力
引導線構圖 leading lines 深度、方向

選一種構圖。

2. 光線：光從哪裡來？

光線類型 英文提示詞 效果
側光 side light 立體感最強
逆光 / 邊緣光 back light / rim light 營造氛圍、強調輪廓
頂光 top light 製造壓迫感
底光 under light 詭異、不自然

全圖有一個主光源。光線選得好，畫面就好。

3. 景深：誰清楚、誰模糊？

景深類型 英文提示詞 效果
淺景深 shallow depth of field 突出主體，電影感
深景深 deep depth of field 前後都清楚
焦點在眼睛 focus on eyes 情緒感最強

有一處焦點，分清楚主次關係。

4. 視角：從哪裡看？

視角 英文提示詞 效果
平視 eyelevel view 最自然
低角度 low angle 讓主體看起來更強大
高角度 high angle 讓主體顯得弱勢、渺小

5. 主體：誰在畫面裡？

用特徵描述，而不是角色名。

· 不寫：Hatsune Miku
· 改寫：extremely long teal twintails, black pleated skirt, digital idol aesthetic

為什麼？因為 DiT 模型記住的不是名字，而是特徵的組合。用特徵描述，能更精準地畫出你想要的角色。

6. 環境：在哪裡？

簡單交代場景：河邊、城市街道、森林、房間……

7. 細節：有什麼額外的亮點？

道具、表情、天氣、氛圍等。

---
## 第四部分：一個特別的案例——閾值空間

有時候，我們想要的不是有角色的場景，而是一種氛圍。比如閾值空間（Liminal Space）——那些空無一人、讓人感到詭異和不安的過渡空間：空蕩蕩的走廊、無人的停車場、凌晨的便利商店。

這類場景有一個有趣的特性：引導線構圖 + 沒有人物主體。當這兩個條件同時滿足時，AI 會自動走到閾值空間這個區域裡面，生成那種獨特的詭異氛圍。

對比示例

普通寫法：

```text
empty hallway, fluorescent light, no people
```

結果可能只是一張普通的空走廊照片，沒有那種不對勁的感覺。

設計圖式寫法（按結構優先順序）：

1. 構圖：引導線 + 消失點
   leading lines, vanishing point
2. 光線：冰冷的日光燈
   harsh fluorescent ceiling light, cold artificial illumination
3. 景深：前後都清楚
   deep depth of field, everything in focus
4. 視角：監視器角度
   surveillance camera angle, highangle shot
5. 主體：無人
   no people, empty corridor
6. 環境：廢棄的醫院走廊
   abandoned institutional corridor, endless repeating doorways
7. 細節：停滯的空氣、壓抑的寂靜
   stagnant air, oppressive silence, dusty air particles in light beams

完整 Prompt：

```text
leading lines, vanishing point, harsh fluorescent ceiling light, cold artificial illumination, deep depth of field, everything in focus, surveillance camera angle, highangle shot, empty institutional corridor, no people, endless repeating doorways, abandoned hospital hallway, cold clinical color palette, desaturated tones, raytraced reflections on linoleum floor, dusty air particles in light beams, eerie atmosphere, stagnant air, oppressive silence
```

關鍵點

當你用引導線 + 無人這個組合時，AI 會自動進入閾值空間，幫你補上所有相關的氛圍細節——冷色調、灰塵、壓抑感、監視器視角……這些都不是你寫的，而是模型自動填充的。

這就是設計畫面的威力：你給出正確的結構條件，AI 就會自動去到你想去的地方。

---
## 第五部分：進階一步——用 ControlNet 鎖死結構

上面講的是用文字去控制。但文字有時不夠精確，比如你想讓人物擺一個非常具體的姿勢，或者你想讓畫面構圖完全模仿一張你喜歡的電影海報。

這時，就需要一個叫 ControlNet 的工具。

ControlNet 的作用

Prompt 決定畫什麼，ControlNet 決定怎麼擺。

它就像給 AI 一張骨架，讓 AI 必須照著這個骨架來畫，從根源上解決畫面不穩定的問題。

最常用的三種 ControlNet

類型 作用 說明
OpenPose 控制人物姿勢 讀取骨架圖，讓 AI 生成的角色擺出一樣的姿勢
Canny / Lineart 控制構圖邊緣 讀取邊緣線條圖，繼承參考圖的構圖和輪廓
Depth 控制空間深度 讀取深度圖，讓畫面更有立體感

使用 ControlNet 的極簡流程

1. 先寫好你的 Prompt（用上面學到的七個步驟）
2. 找一張參考圖（姿勢、構圖或空間感）
3. 在生圖工具（如 ComfyUI、WebUI）裡打開 ControlNet，上傳參考圖，選對應的模型（OpenPose / Canny / Depth）
4. 調整權重（weight）——通常預設 0.7 左右，過高會不協調

---
## 第六部分：實戰案例——從初音到河邊的她

我們來看看，用這套思維去設計一個畫面，會是什麼效果。

目標：畫一個初音，夜晚在河邊。

SD / SDXL 式寫法

```text
Miku, night, riverside, anime style
```

對於 DiT 模型，這只能亂猜：姿勢？光線？構圖？都不知道。結果就是碰運氣。

設計圖式寫法（按結構優先順序）

1. 構圖：不對稱構圖，人物偏左，右邊留給河面
   asymmetrical composition, subject on left third
2. 光線：月光，皮膚有通透感
   ambient moonlight, subsurface scattering lighting
3. 景深：只有眼睛清楚，背景模糊
   sharp focus on eyes, shallow depth of field
4. 視角：平視
   eyelevel view
5. 主體：用特徵描述代替角色名
   1girl, extremely long teal hair in twintails, sleeveless white top, black pleated skirt, glossy black thighhigh stockings
6. 環境：河邊，夜晚
   riverside at night, distant river
7. 細節：回頭看，微笑，河面反光
   looking back over shoulder, faint smile, faint reflections from the water

完整 Prompt

```text
asymmetrical composition, subject on left third, ambient moonlight, subsurface scattering lighting, sharp focus on eyes, shallow depth of field, eyelevel view, 1girl, extremely long teal hair in twintails, sleeveless white top, black pleated skirt, glossy black thighhigh stockings, riverside at night, looking back over shoulder, faint smile, distant river, faint reflections, 16:9
```

---
## 第七部分：什麼時候用角色名，什麼時候不用？

這是一個常見的困惑。我們來釐清：

不推薦直接用角色名的情況

· 當你用的是 DiT（tsubaki / tsubaki.2 / FLUX ） 這類新模型時——這類模型對特徵組合更敏感，用特徵描述效果更好
· 當你不想被訓練數據綁架時——角色名會把結果鎖死在訓練集中的平均版本上，給你一個最沒有新意、最沒有辨識度的角色

可以保留角色名的情況

· 當你用 Stable Diffusion / SDXL 時——SD 系列對角色名有強烈的記憶對齊，用名字反而更穩定
· 當你想要 100% 還原某個特定版本時——這種情況下，用 LoRA 會比單純寫名字更精準
· 當你配合負面 prompt使用時——比如寫 A 角色服裝 + B 角色髮型，用負面 prompt 拉開距離

一個簡單的判斷標準

目標 做法
想讓模型自由發揮、有靈氣 用特徵組合，不用角色名
想讓模型穩定復刻、不跑偏 用角色名，或直接用 LoRA

在我們上面的初音案例中，用的是特徵組合，而不是直接寫 Hatsune Miku。這樣做的好處是：AI 會落在初音的區域內，但不被某個具體版本鎖死，結果既有角色感，又有新鮮感。

---
## 第八部分：懶人結論——如果你只記三件事

第一件事：改變思維

從列購物單變成設計畫面。先想結構（構圖、光線、景深），再填內容（主體、環境、細節）。

第二件事：七步結構法

每次寫 Prompt，都按這個順序問自己：

構圖 → 光線 → 景深 → 視角 → 主體 → 環境 → 細節

第三件事：善用工具

當文字控制不夠精確時，用 ControlNet 去鎖死結構。Prompt 告訴 AI 畫什麼，ControlNet 告訴 AI 怎麼擺。

---
## 結語

你用 AI 生圖畫不好看，不是因為模型不會畫，而是你沒有讓它知道該怎麼畫。

90% 的問題都不是 Prompt 詞彙不夠，而是沒有畫面結構。

把你想要呈現出來的畫面，放在生成之前去思考，你的圖就會穩定很多。
