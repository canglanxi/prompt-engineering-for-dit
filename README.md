# prompt-engineering-for-dit
DiT模型（Tsubaki.2 /FLUX.1 / FlUX.1Dev）AI生圖系統化教程：七步結構法、原型導航、光照六層級、τ-Gen提示詞轉譯器

# τ-Gen (Tau-Gen)

一套基於擴散模型生成機制的「泛化導航」協議

---

## 一句話理解 τ-Gen

τ-Gen = 用結構化協議，引導生成過程落在「泛化區域」，避開「平均區域」。

τ-Gen 不是一個 prompt，也不是一個 LoRA，而是一套**可複現、可遷移、可改進**的生成控制方法論。它只試圖回答一個問題：

> 當模型越來越強，為什麼我們反而更容易得到平庸、安全、生硬的結果？

---

## 核心觀察

擴散模型的生成是從高維噪聲向低維圖像**坍塌**的過程：

- **前 20% 的 prompt** 決定骨架（構圖、光線、景深）
- **後 80% 的 prompt** 填充血肉（主體、環境、細節）

如果骨架模糊，模型會默認落在**平均區域**——穩定、安全、但平庸。

τ-Gen 的目標是：**讓 prompt 成為結構說明書，而不是購物清單。**

---

## τ-Gen 協議（四大核心）

| 協議 | 全稱 | 作用 |
|------|------|------|
| **TPW** | Token Position Weight | 結構詞（構圖/光線/景深）強制放在 prompt 前 20%，釘死坍塌方向 |
| **AN** | Archetype Navigator | 角色名 → 特徵組合，導航到「泛化區域」，避免記憶僵化 |
| **PMI** | Physical Material Injector | 刪除評價詞（masterpiece/8k），注入物理參數（SSS/各向異性反射） |
| **CA** | Contrast Anchor | 三分法構圖時補充「負空間」描述，降低背景語義熵 |

這些協議共同對抗一個問題：**模型的「平均化引力」。**

---

## 怎麼用 τ-Gen？

最簡流程（適用任何 DiT 架構模型，如 Tsubaki.2、Flux、SD3.5）

### 1. 寫 prompt 前，先問自己七個問題（按順序）

> 構圖 → 光線 → 景深 → 視角 → 主體 → 環境 → 細節

### 2. 把前三個（構圖/光線/景深）放在 prompt 的最前面

這是 TPW 協議的核心：前 20% token 釘死結構

### 3. 用特徵描述取代角色名

- 不寫「Hatsune Miku」
- 寫「teal twin-tails, black pleated skirt, digital idol aesthetic」

### 4. 刪除「masterpiece / best quality / 8k」這類評價詞

它們是「平均化引力」的來源

### 5. 如果文字不夠精確，用 ControlNet 鎖死結構

- OpenPose（姿勢）
- Canny（構圖）
- Depth（空間深度）

---

## 範例對比

### 購物清單式寫法（容易落入平均區）

```

Miku, night, riverside, anime style

```

### τ-Gen 結構式寫法（導航到泛化區）

```

asymmetrical composition, subject on left third,
ambient moonlight, subsurface scattering lighting,
sharp focus on eyes, shallow depth of field,
eyelevel view,
1girl, extremely long teal hair in twintails,
sleeveless white top, black pleated skirt,
glossy black thighhigh stockings,
riverside at night, looking back over shoulder,
faint smile, distant river, faint reflections

```

**差異**：第二個版本不是列清單，而是先給結構、再填內容。

---

## 驗證過的模型 / 平台

| 模型/平台 | 狀態 |
|----------|------|
| pixAI Tsubaki.2 (DiT) | ✅ 已驗證 |
| Flux | ✅ 理論適用（待實測） |
| SD3.5 | ✅ 理論適用（待實測） |
| qwen (L 站) | ✅ 跨平台驗證完成 |
| SD / SDXL | ⚠️ 部分適用（角色名建議保留） |

---

## 這個 Repository 包含什麼

```

tau-gen/
├── README.md                    # 你正在看的這份README
├── LICENSE                      # CC BY-NC-SA 4.0
├── docs/
│   ├── theory/                  # 理論篇
│   │   ├── diffusion_dialogue.md      # 與擴散模型對話
│   │   ├── archetype_navigation.md    # 原型導航法
│   ├── tutorials/               # 教程篇
│   │   ├── beginner_zh.md       # 入門教程（中文）
│   │   └── beginner_en.md       # 入門教程（英文）
│   └── tools/                   # 工具篇
│       └── decision_translator_v1.1.md  # τ-Gen 整合版轉譯工具

```

---

## 核心概念速覽

| 概念 | 簡化解釋 |
|------|---------|
| **泛化** | 模型學到規律，能舉一反三 → 有靈氣 |
| **記憶** | 模型鎖定具體訓練樣本 → 穩定但僵硬 |
| **平均** | 模型找不到方向，取最安全折衷 → 平庸 |
| **原型吸引子** | 潛在空間中穩定的高概率區域，用特徵組合即可到達 |
| **坍塌順序** | 前 20% 決定結構，後 80% 填充細節 |

詳細說明請參考 `docs/theory/` 下的文件。

---

## 為什麼叫 τ-Gen？

τ（tau）在擴散模型文獻中常代表「時間步」或「泛化時間閾值」（τ_gen）。

τ-Gen 的命名隱含兩個意義：

1. **時間順序**：prompt 的結構必須符合生成過程的坍塌順序
2. **泛化導航**：引導模型落在 τ_gen 窗口內的泛化區域，而不是記憶或平均區域

---

## 授權

本專案採用 **CC BY-NC-SA 4.0** 授權。

- **BY**：使用時必須註明原作者（潤熙 / Runxi）
- **NC**：不可用於商業用途（如需商業授權，請聯繫作者）
- **SA**：改作後必須以相同授權釋出

詳見 [LICENSE](LICENSE) 文件。

---

## 引用

如果你在文章、專案或研究中使用了 τ-Gen，請引用：

> 瀾熙 (Lanxi). (2026). *τ-Gen: 基於擴散模型生成機制的泛化導航協議*. Retrieved from [GitHub 連結]

---

## 聯絡

- Discord: 瀾熙 (canglanxi)
- 平台 pixAI https://pixai.art/zh/@canglanxi/artworks

---

## 更新紀錄

| 版本 | 日期 | 內容 |
|------|------|------|
| v1.0 | 2026-03-31 | τ-Gen 協議首次公開（TPW/AN/PMI/CA） |
| v1.1 | 2026-03-31 | 整合決策轉譯工具，新增跨平台驗證案例 |
| v1.3 | 2026-04-08 | 整合決策轉譯工具，部分模型移除權重類型 |
```
