# 概要
某サロンでチーム開発するときの設定

基本的には、GitHubのforkとPull Requestを使って作業します。

- fork元: data-learning-guildが所持しているリポジトリ
- fork先: 自分のリポジトリ

## 開発の大まかな流れ
1. 開発対象のリポジトリを各自forkして、fork先でブランチをつくって開発。
2. 担当の機能を実装したら、fork先のブランチに変更をpush
3. Pull Requestをfrok元に送る
4. リーダーがコードレビューして、OKならmain(*1)ブランチにmergeする




(*1) [最近は、masterという言葉が差別を想起させるので、なるべく使わないほうがベター。](https://news.yahoo.co.jp/articles/184ec1a8a925d7c7f5ae09ec60193e46cd62a1d3)
ちなみに、ブラックリスト、ホワイトリストも同様。



# メンバーが開発するために必要な知識

大体、 [Issue とプルリクエストでのコラボレーション](https://docs.github.com/ja/github/collaborating-with-issues-and-pull-requests)
からのリンク

## fork関連

### STEP1
[リポジトリをフォークする](https://docs.github.com/ja/github/getting-started-with-github/fork-a-repo)を試して、forkしてください。

### STEP2
次にfork先のリポジトリでブランチをつくってください。
GitHub上で直接触るなら、[リポジトリ内でブランチを作成および削除する](https://docs.github.com/ja/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository)を参照してください。
もちろん、gitのコマンドでも作成可能です。

開発が終わったら、brunchにcommitして[fork先のリポジトリにpush](https://docs.github.com/ja/github/using-git/pushing-commits-to-a-remote-repository#renaming-branches)してください。


### STEP3

[フォークからプルリクエストを作成する](https://docs.github.com/ja/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)
を参考にして、Pull Requestを作成してください。

Pull Requestを送ったら、レビュー担当の人にメッセージを送っておくと親切です。  
->STEP4参照

Pull Requestが却下された場合は、branchに再度変更を加えてから、pushして、再度Pull Requestを出してください。使用するbrunchはそのままでいい場合が多いはずです。

# リーダー編
その機能に責任を持つ人。セキュリティ周りの知識があるとベターです。  
例) GCPのService Accoutn keyなどの秘匿情報が入っていた場合は、削除指示と、秘匿情報の再設定をしてほしいです。

下記に筆者のおすすめのワークフローの設定を書きます。
ワークフロー自体は、リーダーを中心として各リポジトリごとで決めてください。


## きちんとレビューするワークフローの構築 

色々方法がありますが、比較的シンプルな [GitHub Flow](https://thinkit.co.jp/article/8410)を前提とします。

### main brunchの保護
きれいな状態(≒リリースできる状態)のbrunchを一つ決めておき(GitHub Flowではmain brunch)、そのブランチに対しては直接変更できないように設定できます。

[保護されたブランチを設定する](https://docs.github.com/ja/github/administering-a-repository/configuring-protected-branches)

### レビュワーの割当
CODEOWERで必ずレビューする人(達)です。
レビュー対象をファイルごとに設定をできます。
[コードオーナーについて](https://docs.github.com/ja/github/creating-cloning-and-archiving-repositories/about-code-owners)を参照してください。


## STEP4 
[必須レビューでのプルリクエストの承認](https://docs.github.com/ja/github/collaborating-with-issues-and-pull-requests/approving-a-pull-request-with-required-reviews)を参考にして、レビューしてください。
だめな場合は、[feedbackを書くか](https://docs.github.com/ja/github/collaborating-with-issues-and-pull-requests/commenting-on-a-pull-request)書いたり、直接メッセージを送ったりZoomで連絡してください。

Pull Requestが承認されてMergeされたブランチを残すか消すかは各リポジトリでルールを決めてください。


