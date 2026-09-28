---
context_version: 1
source_repository: mikami-takashi-saitamacity/council-activity-private
source_commit: 4386352a38a3eaebfa89b3d5e9b89d6db0333e36
generated_at: 2026-09-28T12:56:28+09:00
visibility: shared
---

# CURRENT_CONTEXT_SHARED

このファイルは上記source_commitの入力から生成した参照用スナップショットです。
仕様判断は確定判断、現行仕様、実装現物の順に照合してください。
source_commitは生成commit後のHEADではなく、このファイル内部の値を表示してください。
取得できない場合、会話記憶や旧HANDOFFだけで仕様判断を続けないでください。

公開DB v1.3.0: 2026-09-28に1,343件で正式公開。
議事録718件、予算提案625件。v1.3.0の公開データ・schemaは別repoの現物を参照。

PRIVATE未参照。内部の未公開判断が関連する場合は、その限界を明示してください。

## _decisions/D-20260928-CAUSAL-ATTRIBUTION.md

---
id: D-20260928-CAUSAL-ATTRIBUTION
status: accepted
date: 2026-09-28
scope: [site, db]
target_version: undecided
summary: >
  後年の市の施策・事業の変化を表示する際、見出しは「その後の市の動き」等とし、
  三神の質問・提案との因果関係は主張しない（causal_attribution の既定値は not_asserted）。
  「成果」「実現させた」等の表現は用いない。因果を示すのは、答弁・行政資料等が
  三神の提案を明示的に参照している場合に限り、その根拠資料を必須とする。
supersedes: none
related_files: []
publish_scope: shared
---

# 後年の市の動きと因果関係の表示

三神が2026-09-28に承認した表示方針。次期版のfield名、enum、schema、実装時期は未決定。

## _decisions/D-20260928-HUMAN-VERIFICATION-BADGE.md

---
id: D-20260928-HUMAN-VERIFICATION-BADGE
status: accepted
date: 2026-09-28
scope: [site, db]
target_version: undecided
summary: >
  人手で原文との照合を確認したカードにだけ確認済み表示を付ける。
  AIのみの照合や公開候補の段階的承認をカードごとの人手確認とみなさない。
supersedes: none
related_files: []
publish_scope: shared
---

# 確認済み表示

未確認カードに確認済みバッジを付けず、「照合中」等の表示も必須としない。field名、review workflow、schema、表示実装、版番号は未決定。

## _decisions/D-20260928-RAW-BOUNDARY.md

---
id: D-20260928-RAW-BOUNDARY
status: accepted
date: 2026-09-28
scope: [workflow, db]
target_version: undecided
summary: >
  raw会議録・全文・本文の再構成物をGitHubへ置かない。
  ssp.kaigiroku.netへの自動アクセスを行わない。
supersedes: none
related_files: []
publish_scope: shared
---

# 原資料の境界

保存TXT、PDF、ZIP、原文本文と大量の本文断片はCURRENT_CONTEXTに含めない。原文を要する照合では別途保存資料や公式原文を確認する。保存TXT内のURL文字列をローカルで抽出することは、この自動アクセス禁止に含まれない。

## _decisions/D-20260928-RESULT-LEVEL-IMMUTABLE.md

---
id: D-20260928-RESULT-LEVEL-IMMUTABLE
status: accepted
date: 2026-09-28
scope: [db, site]
target_version: undecided
summary: >
  result_level は質問・提案に対する当時の答弁・回答に基づく評価とし、
  後年の情報で「実施済」等へ上書きしない。後年の市の動きは当時評価と
  区別して扱う。当時資料の読み違い等、当時の判定自体の誤りを根拠に
  基づいて訂正することは、後年の進展による再評価と区別する。
supersedes: none
related_files: [v1.2.0/specs/budget_step10_spec.md]
publish_scope: shared
---

# 当時の評価と後年の動き

三神が2026-09-22に承認した予算提案の現行仕様（`v1.2.0/specs/budget_step10_spec.md`「評価の基準時点と将来の追跡評価」）を、共通の判断INDEXへ登録する。議事録も答弁時点と後年の進展を区別する。既存議事録の評価に後年の再判定が混入していないかは、版別の監査資料を確認する。この判断だけをもって全カードの時点整合が監査済みとみなさない。

- 当時の評価は、その質問・提案に対する当時の答弁・回答を根拠とする。提案時点や現在の状態と混同しない。
- 後年に事業が実施・改善された場合も、当時の`result_level`をその事実だけで「実施済」等へ変更しない。後年の動きは別のレイヤーで記録・表示する。
- 当時資料の読み違い等が確認された場合は、当時の判定の訂正と後年の進展による評価更新を区別し、訂正の根拠を残す。後年の実現を「当時の判定の誤り」と呼び換えない。
- 追跡評価のフィールド、変更履歴の保存形式、サイト表示、版番号、実装時期は後続工程で定める。今回の判断は公開DBやschemaの改訂を意味しない。

## _decisions/D-20260928-SOURCE-OF-TRUTH.md

---
id: D-20260928-SOURCE-OF-TRUTH
status: accepted
date: 2026-09-28
scope: [workflow, db, site]
target_version: undecided
summary: >
  仕様・決定の唯一の正本はcouncil-activity-privateのmainとする。
  AIの会話記憶、旧HANDOFF、Project内の古い資料より優先する。
supersedes: none
related_files: []
publish_scope: shared
---

# 仕様と判断の正本

仕様判断はprivate mainの`_decisions/INDEX.md`、現行仕様、実装現物の順に確認する。CURRENT_CONTEXTはそのcommitの参照用スナップショットであり、取得に失敗した場合は記憶から仕様を補わない。
