[[AJACS10]]に戻る
        --
- [[データベースを使いこなすためのコンピュータ・ウェブの基本的な使い方>./basic]]
- [[統合データベース>./togo]]
- [[文献データベース>./paper]]

- [[世界中の代表的なデータベース・ツール>./DB]]
- [[ホモロジー検索（BLAST）>./BLAST]]
- [[マルチプルアラインメント>./ClustalW]]
- [[モチーフ検索>./motif]]
- [[ゲノムブラウザ>./gb]]
- [[遺伝子発現解析>./expression]]
- [[パスウェイ解析>./pathway]]
- [[タンパク質立体構造>./structure]]

- ''その他''↓
        --
#contents
        --

# 機能アノテーションの方法 [#mc4a12b2]
#ref(AJACS10.008.jpg)

# 現在進行中のゲノムプロジェクトを調べる　～GOLDデータベース～ [#ba426fce]

#ref(AJACS10.060.jpg)

- [[GOLD: Genomes OnLine Database>http://www.genomesonline.org/]]
    -世界中で行われた／行われているゲノムプロジェクトを集めたデータベース
- 統合TV： http://togotv.dbcls.jp/20090403.html

- 【演習】：解読が終了したゲノムプロジェクト・現在進行中のゲノムプロジェクトを調べてみましょう
    -真ん中にある「GOLD Tables」をクリックすると、終了したゲノムプロジェクトの数と、それぞれの生物ドメイン（真核／真正細菌／古細菌）で進行中のゲノムプロジェクト数が見れます

    -すでに終了しているプロジェクトはいくつありますか？
    -真核生物で現在進行中のゲノムプロジェクトはいくつありますか？
    -真正細菌、古細菌で進行中のプロジェクトはいくつありますか？

        -真核生物：Eukaryote (E)
        -真正細菌：Bacteria (B)
        -古細菌：Archaea (A)

- メタゲノムプロジェクト（ある場所にいる生物のゲノムをまとめて読む）の数も見れます
    -どのような場所の生物集団が対象になっていますか？調べてみましょう

- 【演習】：あの生物（犬とかネコとか）のゲノムは読まれているか？調べてみよう。
    -まず、調べたい生物の学名（ヒトの場合だとHomo sapiens）を調べます
        -catとかdogのような一般名では調べられません
        -大抵[[WikiPedia>http://ja.wikipedia.org/]]とかに載ってます
        -NCBIの[[taxonomy>http://www.ncbi.nlm.nih.gov/Taxonomy/]]とかでも調べられる

    -「属」の部分（ヒトの場合だと Homo）をコピーします
        -sapiensの部分は「種」といいます

    -GOLD Tablesの真ん中へんに「Search GOLD」というのがあるのでクリック
        -「Genus」（属）の部分にペーストして「Submit search」をクリックすると検索できます
        -「species」（種）も指定できますが、検索条件をきつくしすぎると、結果が帰ってこないかもしれません

    -調べたゲノムプロジェクトは終了していましたか？進行中でしたか？それとも誰もやっていない？

        --

# [[GO: Gene Ontology>http://www.geneontology.org/]] [#i6e4677f]

#ref(AJACS10.063.jpg)
#ref(AJACS10.064.jpg)

- &color(green){遺伝子機能を説明するための用語集で階層構造になっています。evidence が明記されているのはすばらしいこと}
    -biological process: 生物学的プロセス
    -cellular component: 細胞の構成要素
    -molecular function: 分子機能

- エビデンスコード（信頼性基準）
    -IDA: Inferred from Direct Assay
    -IMP: Inferred from Mutant Phenotype
    -ISS: Inferred from Sequence or Structural Similarity
    -RCA: inferred from Reviewed Computational Analysis
    -TAS: Traceable Author Statement
    -NAS: Non-traceable Author Statement
    -IEA: Inferred from Electronic Annotation
などなど

- 入力ボックスに遺伝子名やGOの用語を入力して検索できます

- 【演習】：「amylase」を「GO term or ID」から検索してみましょう
    -用語中に「amylase」を含んでいるGO用語がリストされます
    -一番上の「amylase activity」をクリックすると
        -all : all  [251269 gene products]
        -GO:0003674 : molecular_function [164180 gene products]
        -GO:0003824 : catalytic activity [48760 gene products]
        -GO:0016787 : hydrolase activity [15758 gene products]
        -GO:0016798 : hydrolase activity, acting on glycosyl bonds [1346 gene products]
        -GO:0004553 : hydrolase activity, hydrolyzing O-glycosyl compounds [1008 gene products]
        -GO:0016160 : amylase activity [69 gene products]

    -という階層構造を持ち、現在その中には69個の遺伝子が登録されていて、

    -「[69 gene products]」の部分をクリックすると、登録されているそれぞれの遺伝子が「amylase activity」を持つ、とされた根拠が信頼性（エビデンスコード）とともに表示されます


+【演習2】：キーワード「DNA binding circadian」で検索してみよう
++結果のなかから CCA1, CIRCADIAN CLOCK ASSOCIATED 1 をクリックして遺伝子の詳細を見る
++上部の「5 term associations→」リンクを開いてGene Associationとevidence codeを閲覧
++GO:0007623 の「circadian rhythm」をクリックして[[GeneOntology>http://www.geneontology.org]]の詳細を見る
++Term Lineageの「circadian rhythm [243 gene products] 」のリンクをクリックし、
++このタームに関連する遺伝子のリストを表示する<br>
【ここでも、それぞれのevidence codeに着目してみよう】
++Evidence CodeをIDA (Inferrd from Direct Assay) に限定するfilterをかけてみる
++speciesをA. thalianaに限定してみるなどの操作を行ってみる
++IDA, TASなど、複数のEvidence codeの選択も可能。Macならcommand key+クリック,windowsの場合はCtrlかShiftあたりか？

- 【発展】: Evidence Codeの詳細を[[Guide to GO Evidence Codes>http://www.geneontology.org/GO.evidence.shtml]]を参照して確認しよう。あなたにとって信頼に足るcodeはどこまでか


//**[[CyanoGenes:http://bacteria.kazusa.or.jp/cyanobase/Synechocystis/comments/]] [#v0863dd0]

//&color(green){シアノバクテリアの遺伝子単位のコメント受付。オープンアノテーションの最初期の試み};

//>http://www.kazusa.or.jp/cyanobase/Synechocystis/comments/

//-【実習】: それぞれの遺伝子にどんなコメントがついているか、確認してみよう


//**[[KazusaAnnotation:http://a.kazusa.or.jp]] [#ca5bb518]

//&color(green){統合DBプロジェクトにおける、オープンアノテーションへの挑戦。現在進行形};

//>http://a.kazusa.or.jp

//-【実習】: それぞれの遺伝子にどんなブックマークとコメントがついているか、確認してみよう

        --


# コンピュータ上でベクターに遺伝子を導入する [#v46ca7d7]
- EMBOSSのtranseq, revseq
- Primer3
- NEBcutter
    -を使ってベクターへの遺伝子導入をコンピュータ上のシミュレーションする

#ref(AJACS10.049.jpg)
#ref(AJACS10.050.jpg)
#ref(AJACS10.051.jpg)

- 酵母(Saccharomyces cerevisiae)のost4という遺伝子の全長を発現ベクターに導入してみる（Ost4タンパク質は34アミノ酸残基からなるとても短いタンパク質です）

- 演習用配列1（coding sequence）
 >YDL232W  Chr 4
 ATGATCTCTGATGAACAGCTGAACTCCTTGGCCATCACCTTCGGTATTGTGATGATGACT
 TTAATTGTCATTTACCATGCTGTTGACTCCACCATGTCTCCTAAGAACTAA

## [[EMBOSS>http://emboss.sourceforge.net/]] [#v3687d63]
- 200以上の配列解析ツールを収録したプログラム集
- 左側からツールをクリックしたときに、右側の画面のツール名の下に出る(read the manual)をクリックすると、ツールの説明やオプションの説明、実行例などが見れます（英語ですが・・・）

## transeq でDNA配列をアミノ酸に翻訳してみる [#gd1b21d1]
- 統合TV：[[transeqで塩基配列をアミノ酸に変換する>http://togotv.dbcls.jp/movie/071120transeq_f.html]]

- [[transeq (EBI)>http://www.ebi.ac.uk/Tools/emboss/transeq/index.html]]

- [[EMBOSS Explorer @ DBCLS>http://emboss.dbcls.jp/]]

    -Frame(s) to translate で翻訳するフレームを選択します
        - 1:入力した配列を最初から翻訳していきます
        - 2:2番目の塩基から翻訳を開始します
        - 3:3番目の塩基から翻訳を開始します
        - Foward three frames:上記3つの翻訳を一度に実行します
        - -1:入力した配列の相補配列を最初から翻訳していきます(入力した配列の最後から翻訳されます)
        - -2:入力した配列の相補配列の2番目の塩基から翻訳していきます(入力した配列の後ろから2番目の塩基から翻訳されます)
        - -3:入力した配列の相補配列の3番目の塩基から翻訳していきます(入力した配列の後ろから3番目の塩基から翻訳されます)
        - Reverse three frames:上記3つの翻訳を一度に実行します
        - All six frames:すべてのフレームを一度に翻訳します

    -Code to use で翻訳コードを指定します（ミトコンドリアの遺伝子などは通常のコドンテーブルが使えない場合が多いです）

    -Regions to translate で翻訳する領域を指定できます


- 【課題】: 演習用配列1をアミノ酸に翻訳しなさい。全てのフレームで翻訳するとどうなるか？

## Primer3でプライマーを設計する [#j2f18ab0]
- 統合TV：[[Primer3でPCR用のプライマーを設計する>http://togotv.dbcls.jp/20070824.html]]

- [[Primer3>http://www.bioinformatics.nl/cgi-bin/primer3plus/primer3plus.cgi]]

    -左上にある「Task」から目的にあわせてプライマー設計が可能
        -Detection: 通常のPCR用プライマー
        -Cloning: フレームを指定してクローニングしたいとき用
        -Sequencing: シーケンス用のプライマー（プライマーの間隔とかを調整）
        -Primer List: 見つけたプライマーのリストを表示
        -Primer Check: プライマーの長さ、tm値、GC含量などを計算

    -「Main」タブ
        -Excluded Regions: <>　で囲んだ配列からはプライマーを設計しない
        -Targets: []　で囲んだ配列を含むようにしてプライマーを設計する
        -Included Region: {}　で囲んだところからプライマーを設計する

    -「General Setting」タブ
        -プライマーの長さ、Tm値、GC含量の範囲などを指定できる

    -「Advanced Setting」タブ
        -分子内にいくつまで相補的な配列を許すか、などを指定できる

    -右上の「Pick Primer」でプライマーを設計する

- 演習用配列2（ost4とその上流、下流のDNAを含む：全長をクローニングする際には遺伝子の前後の配列が必要となる）
 >YDL232W  Chr 4
 TGCAAGTCAGTAGAGAAACCCAGTACAGAGCAAGCAAAAGATGATCTCTGATGAACAGCT
 GAACTCCTTGGCCATCACCTTCGGTATTGTGATGATGACTTTAATTGTCATTTACCATGC
 TGTTGACTCCACCATGTCTCCTAAGAACTAAAGTGGTTACATTTGGATAGCGAACTTCAG

- 【課題】: ost4をコードしている部分を増幅するプライマーを設計せよ。
    -今回はフレームは考えないことにするので、Task: はDetectionにする
    -演習用配列1を参考にしてコードされている部分を[]で囲う
    -パラメータは初期設定で

- 解答
    -&color(white){5'末端側のプライマー：CCCAGTACAGAGCAAGCAAA};
    -&color(white){3'末端側のプライマー：TTCGCTATCCAAATGTAACCA};
 増幅される配列：
 CCCAGTACAGAGCAAGCAAAAGATGATCTCTGATGAACAGCTGAACTCCTTGGCCATCA
 CCTTCGGTATTGTGATGATGACTTTAATTGTCATTTACCATGCTGTTGACTCCACCATG
 TCTCCTAAGAACTAAAGTGGTTACATTTGGATAGCGAA};

### ベクターに導入するために増幅する配列の両末端に制限酵素認識サイト（のりしろ）をいれます [#v1f9e25b]
- 今回は[[pUC18>http://catalog.takara-bio.co.jp/product/basic_info.asp?unitid=U100003189]]という発現ベクターを使ってみます
- 制限酵素は EcoRI, BamHI, HindIII あたりがよく使われます
    -EcoRIの認識配列: GAATTC
    -BamHIの認識配列: GGATCC
    -HindIIIの認識配列: AAGCTT
- これらの配列をのりしろとして使うには、増幅された配列がこれらの酵素で切断されない必要がある


## NEBcutter [#id2dd784]
- 統合TV：[[NEBcutterでDNAを切り倒す！>http://togotv.dbcls.jp/movie/071107NEBcutter_f.html]]

- [[NEBcutter>http://tools.neb.com/NEBcutter2/index.php]]

- 【課題】:設計したプライマーによって増幅される配列が、EcoRI, BamHI, HindIIIで切断されるかされないか確かめてみよう
    -入力ボックスに増幅される配列をコピー＆ペースト
    -左下のチェックボックスで入力した配列が直鎖か環状か指定
        -PCR増幅産物はLinearなのでLinearを選択
    -右側のチェックボックスで制限酵素リストを指定
        -NEB enzymes: NEW ENGLAND BioLabs社で売っている制限酵素
        -All commercially available specificities: 売られている制限酵素
        -All specificities: 今まで発見されている制限酵素
    -「submit」で制限酵素切断部位を検索
    -初期状態では配列を1ヶ所切断する制限酵素が表示される
        -入力配列を''切断しない''酵素のリストは、「0 cutters」から見ることができる

- 配列を切断する酵素を使って、設計通りに正しく配列が増幅したか？を確かめることができる
    -左下「Main Options」の「Custom digest」から、切断に使う酵素を選択
    -例えば「HincII」という制限酵素にチェックを入れて、一番下にある緑色の「Digest」をクリックするとHincIIの切断部位が表示される
        -「View gel」をクリックすると、電気泳動したときにどのようになるかを表示できる
        -電気泳動の画面ではゲルの種類を選んだり、マーカーを同時に表示させたりもできる


### 増幅配列を切断しない酵素がわかったら、どの制限酵素を使うか考えます [#v4ce1090]
- プライマーの5'末端側に制限酵素の認識配列を追加します
    -プライマーの長さ、Tm値、GC含量なども考慮しながら考える


### プライマーのtm値計算ツール [#p5c7a028]
- http://www.m-neko.net/tm_calc/
- http://www.research.kobe-u.ac.jp/brce-mikitani/tm.html
- http://www.riken.go.jp/lab-www/help2/members/kagawa/tmnumber.html

などなど
    -何種類か計算方法があるのでいろいろな値が出てくる。
        -同じ計算方法で同じくらいのtm値になるのが理想

## ベクターにPCR増幅産物を入れたらどうなるか見てみます [#na903a1a]
- NEBcutterのトップページに戻って、灰色の箱の右上にある「Standard sequences:」から、pUC18を選んで「Submit」します
- マルチプルクローニングサイトの部分を拡大して見てみると、なんと遺伝子が読まれる方向とは逆方向に配列が登録されています。これはひどい
- しかたがないので、増幅した配列の相補配列を作ります

## revseq [#a59ee800]
- EMBOSS の revseq を使うと、相補配列、逆配列などを作成できます
    -Complement sequence? を Yes にすると、相補配列に変換できます。ただし、このままでは配列が 3' → 5' の方向を向いています
    -そこで、Reverse sequence? を Yes にして、5'と3'を入れ替えます
- これで''高いソフトを買わなくても''相補配列を手に入れることができます

### それではコンピュータの中で増幅配列をベクターの中に入れてみます [#p193ebc6]
- メモ帳などを使ってコピー＆ペーストで配列を切ったり貼ったりする
    -NEBcutter pUC18のページで「View sequence」をクリックするとベクターの配列がわかります
    -フレームがずれないように気をつける
- 増幅した配列を1カ所、ベクターを1カ所切断（出来上がったプラスミドでは2カ所切断）する制限酵素を使うと、正しい方向で増幅配列がベクターに入ったかどうかわかります
    -例えば CjuI という制限酵素でプラスミドを切ったとき、正しい方向に配列が入っていれば 2539 bpと275 bpの断片ができるはずです。逆方向に入ってしまった場合は 2504 bpと310 bpの断片ができます

        --
[[AJACS10]]に戻る
