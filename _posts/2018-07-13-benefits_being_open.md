---
layout: post
title: オープンソースにすると嬉しいこと
category: essay
---

今の所属研究室での仕事の一つに開発されたコードの知財管理というか、
よっぽどじゃ無い限り全てオープンソースにする事を進める役割をかって出ているのですが、もちろんそんな強硬手段に出るわけにいかないので、基本的にはそれをするとどんないい事があるか、インセンティブを考えないと人って今までワークフローを変えない。(BIM!!)

その関連で、「自身もオープンにする事に傾倒していますので」と一言つけくわえて所長が言っていたオープン（ソース）にしなかった事によって損したOSの話をされていた。いわく、

当時時代を先行して最初のインターネットに完全対応したOSをIBMが作っていたらしく、それに早めにアクセスできたので、所長はそれを早くオープンにしろと執拗に言い寄っていたらしく、結局それは行われず、OSもまあ日の目を浴びず開発は打ち切りになり今日にいたると。

彼らの言い分としては、実はコードの中身は所々不適切なというか恥ずかしい変数名を使っていたり、ロジックの部分も稚拙な所があって到底他所様に見せられるものでは無かったという事だったらしい。

```c
int unko = 0

bool isUnkoOdd(int unco) {
  if (unco % 2 == 1) {
    return true;
  } else {
    return false;
  }
}
```
こんな感じだったんでしょう。学部生とかたまに見ますよね、fu*kとか、コメントじゃなくて変数名に。

論理的に飛躍していますけどね、なんでオープンにしなかったからダメになったと、バイアスかかってます。ほんとのとこ駄目になった理由なんて分からないけど、解釈したのはこうゆうこと:

そもそも最初からオープンにしておけば、そもそもうんこコードを書く事はしなかったでしょう。恥ずかしいからね。そうゆう外部からの力が加わるので、大分読みやすくなると言うことは、そのチームに新人さんが入ってきたときにかかる学習コスト（維持・管理コスト）が軽減される。

と言うか、IBMに入社したい人はそれを入社前に読むしね。もしかしたらわかりにくい所は誰かがコメント描いてくれるかもしれない。会社もそんな人欲しいよね。

もちろん知財と言う名前だけあって、守る必要があるのはいいんだけど、多分潜在的なコストと天秤しないとダメだよね。

何よりも社内と対外的な対応に矛盾（うんこ漏らしてるの隠しながら外ではでかい顔する必要性）が無いから気分もいいよね。透明性って事なんだけど、セキュリティが必要なものほどオープンソースにしたほうがいいと思う。金融関係とか、安全性に関わる自動運転技術とか、建物の構造設計ソフトとか。
ちなみに、暗号化技術は必ず既に確立されているもの使うのがてっぱんで、なぜなら自作で作っても破られるのがおちだから。研究室の中で行われている議論だけど、それを言うなら遺伝子操作の研究をしている人はオープンにして第三国が悪用したらどうするんだ系。まあ、次世代にも影響がありそうな医療系をしている時点でわかっているでしょう。

あとは、真面目にいうと公開してパクられた場合、パクった側が実益得るのはパクった側のほうが開発力の総量が高かった場合(例えば、一人で半日かけたものが次の日にgoogleの社員100人にパクられた場合)だけど、それに対抗するのにちゃんと所定のやりかた（ライセンスといまでいうとコードベースの公開するところgithub?gitlab?どうでもいいけどどっちか）があるからそれを知らなきゃいけないし。

だから、基本公開されていない御コードは上記の様な手段に従い開発が敢行されておると思うことにするよ。（だってそうでしょ）