# Deep Hold'em AI：德州撲克 AI 研究原始碼

> 面向單挑無限注德州撲克（HUNL）的研究型程式碼庫，涵蓋 CFR 子博弈求解、ReBeL 風格遞迴求解、反事實價值網路、自我博弈、監督策略學習與 C++ 蒙地卡羅模擬。

[简体中文](README.md) · [English](README.en.md) · [繁體頁面](https://deeptexas-ai.github.io/deep-holdem-ai/zh-tw/)

![Deep Hold'em AI 牌桌示範](docs/assets/screenshots/masterai-table.jpg)

## 專案定位

Deep Hold'em AI 用於撲克人工智慧、賽局理論與不完全資訊遊戲實驗。公開原始碼包含 HUNL 規則與狀態樹、CFR 子博弈求解器、遞迴求解流程、價值網路、自我博弈資料生成、經驗回放、監督策略網路與 C++ 蒙地卡羅元件。

本專案適合演算法研究、離線訓練、策略評估與教學復現；它不是線上牌局即時輔助工具，也不提供第三方平台辨識、自動操作或規避偵測功能。

## 經原始碼驗證的能力

| 模組 | 功能 | 位置 |
| --- | --- | --- |
| HUNL 引擎 | 52 張牌、四輪下注、棄牌/跟注/多檔加注/全押、終局與牌型評估 | `game/texas_holdem/` |
| CFR 求解 | 遺憾更新、平均策略、最佳回應、可利用度、EV 與到達機率 | `game/subgame_solving.py` |
| 遞迴求解 | 公共狀態子博弈、雙方手牌信念傳播與後續狀態求解 | `game/recursive_solving.py` |
| ReBeL 介面 | 載入價值網路並依公共狀態與信念計算根策略 | `robot/rebel/` |
| 自我博弈 | 多程序資料生成、價值/策略損失、模型同步與回放緩衝 | `cfv/selfplay.py`, `rela/` |
| 監督策略 | 從已求解狀態建立資料集並訓練策略網路 | `supervised_strategy/` |
| 蒙地卡羅 | C++ 模擬器、Python 牌型工具與綁定基礎 | `csrc/mc/`, `robot/gto_mc/` |

## 玩法與演算法流程

引擎建模兩人無限注德州撲克，涵蓋翻牌前、翻牌、轉牌與河牌。公共狀態記錄公共牌、累計下注、目前行動者、可行動作與加注次數。CFR 在子博弈中更新遺憾與平均策略，價值網路估計截斷葉節點；遞迴求解器依實際行動更新私牌信念，並在下一公共狀態繼續求解。

## 訓練配置畫面

下圖為倉庫既有素材，顯示訓練迭代、遺憾參數、剪枝、模型路徑與 Redis 設定；它不是線上牌局辨識畫面。

![Deep Hold'em AI 訓練配置](docs/assets/screenshots/training-config.png)

## 牌桌示範素材

<p align="center">
  <img src="docs/assets/screenshots/poker-table.jpg" alt="Deep Hold'em AI 機器人牌桌示範" width="48%">
  <img src="docs/assets/screenshots/masterai-table.jpg" alt="MasterAI 德州牌桌示範" width="48%">
</p>

圖片僅說明歷史展示形態，不代表對第三方平台的整合或自動操作能力。

## 技術目錄

- `game/`：HUNL 狀態、樹、CFR 與遞迴子博弈求解
- `cfv/`：反事實價值模型與自我博弈訓練
- `rela/`：回放緩衝、資料循環與執行上下文
- `supervised_strategy/`：策略資料集與監督網路
- `csrc/`：C++ 蒙地卡羅模擬及 Python 綁定依賴
- `conf/`：盲注、籌碼、樹深、迭代與網路配置

## 負責任使用

僅限合法研究、教育、離線訓練與基準測試。請勿用於未獲許可的線上即時決策、自動操作、規避平台規則或任何破壞公平性的行為。

## 聯絡方式

- Telegram：[xuzongbin001](https://t.me/xuzongbin001)
- Email：[masterai918@gmail.com](mailto:masterai918@gmail.com)

關鍵字：德州撲克 AI 原始碼、德州 AI、HUNL、CFR 演算法、ReBeL、遞迴求解、自我博弈、撲克機器人、賽局理論。

