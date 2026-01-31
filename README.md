# Project ROOT: Hogwarts Physical Layer Analysis

## 概要

本プロジェクトは、ホグワーツの「貴族ナード」3名による、魔法界というシステムの物理層（Layer-1）からの再記述を目的とする。既存の情緒的・歴史的解釈（UI層）を排し、純粋な物理現象と数理モデルへの置換を行う。

## 基本思想

「眼の前の楽しいことを見つけて仮説を立てて証明していく。他者への説明義務は負わない。」

## 3人の役割（Dependency）

- **アルバス ([char_albus.json](characters/char_albus.json))**: **解体者（Deconstructor）**
  - 既存魔法を数式へ分解。父（ハリー）の「生存者バイアス」を排除し、事実（Fact）を抽出する。
- **スコーピウス ([char_scorpius.json](characters/char_scorpius.json))**: **観測者（Observer）**
  - 歴史と物理の整合性確認。父（ドラコ）から継承した「失敗のログ」を元に、地雷原（リスク）をマッピングする。
- **カトレア ([char_cattleya.json](characters/char_cattleya.json))**: **演算者（Compiler）**
  - 1年生で得た真理を現実世界へ再構成。法的・論理的整合性を担保し、最適化された出力を生成する。

## システム構造（Architecture）

- **[sys_layer_model.json](systems/sys_layer_model.json)**:
  - **L4 (App/UI)**: 英雄譚、寮対抗戦、ジェームズ達の「派手な魔法」。
  - **L3 (Protocol)**: 杖の動き、呪文の詠唱、一般的な教育課程。
  - **L2 (Kernel)**: 古い盟約、城の防衛、ハウスエルフの労働形態。
  - **L1 (Physical)**: 空間の共鳴、遺伝的職能（苗字）、城の石材の物理特性。

### クラス図：システム相関と依存関係

```mermaid
classDiagram
    %% 1. システム基盤レイヤー
    class Global_System {
        <<Directory: systems/>>
        +sys_layer_model.json: レイヤー定義
        +sys_science_magic.md: 魔法数理化論理
        +sys_salvation_logic: 救済定数(100pts)
    }

    %% 2. キャラクター・資産レイヤー
    class Character_Assets {
        <<Directory: characters/>>
        +Decapitalizers: [albus, scorpius, cattleya]
        +Albus_Instances: [Base, Physical, Muscle, Observer]
        +Mentors: [severus_snape_portrait]
        +The_Crystalline: [orinomiya_akiko]
    }

    %% 3. 5年目：マルチバース同期プロトコル (新規追加)
    class Multiverse_Sync {
        <<Intersection: Year_5>>
        +sync_operator: Observer_Albus
        +action: Invitation_to_Yule_Ball
        +target: Cattleya_Shafiq
        +validate_salvation() 100pts_check
    }

    %% 4. 物語進行ロジック
    class Plot_Logic {
        <<Directory: plots/>>
        +plot_Y1: 物理層の解体
        +plot_Y2: 純血のプリンセス (※基底限定)
        +plot_Y3: 世界観測
        +plot_Y4: バリツ(基底)／対抗試合(Y2分岐)
        +plot_Y5: ボーイ・ミーツ・ガール (※全域同期)
        +plot_Y6: テラフォーミング (※基底限定)
        +plot_Y7: 覚者ニルヴァーナ (※基底限定)
    }

    %% --- 依存関係・相互作用の定義 ---

    %% 5年目の同期が各アルバスとスネイプを繋ぐ
    Multiverse_Sync ..> Character_Assets : "全Albusの身一つでの決断"
    Multiverse_Sync ..> Global_System : "救済定数の書き換え(100点)"

    %% プロットと実行の繋がり
    Plot_Logic ..> Multiverse_Sync : "5年目に同期プロトコルを実行"

    %% 既存の依存関係
    The_Crystalline ..> Global_System : "物理定数の『織り直し』"
    The_Crystalline ..> Character_Assets : "解体行為への干渉"
    Plot_Logic ..> Character_Assets : "基底世界ルートの記述確定"

```
