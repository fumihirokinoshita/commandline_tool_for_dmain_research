# commandline_tool_for_dmain_research

## 環境設定(Mac)

go のインストール
```
$ brew install go
```

Path の設定
```
$ mkdir $HOME/go
$ echo 'export GOPATH=$(go env GOPATH)' >> ~/.bash_profile
$ echo 'export PATH=$PATH:$(go env GOPATH)/bin' >> ~/.bash_profile
$ source ~/.bash_profile
```

clone
```
$ mkdir $HOME/go/src
$ cd $HOME/go/src
$ git clone github.com/fumihirokinoshita/commandline_tool_for_domain_research
```

## 動作確認

#### sprinkle
入力した単語の前後にドメインっぽい単語を追加する
```
$ cd $HOME/go/src/commandline_tool_for_domain_research/sprinkle
$ go build -o sprinkle
$ ./sprinkle
```

#### domainify
入力した単語の後ろにTLDを追加する(net or com: availableで検索するwho is serverに対応しているのがこの二つのTLDのみであるため)
```
$ cd $HOME/go/src/commandline_tool_for_domain_research/domainify
$ go build -o domainify
$ ./domainify
```

#### coolify
入力した単語の母音の数を増減させる
```
$ cd $HOME/go/src/commandline_tool_for_domain_research/coolify
$ go build -o coolify
$ ./coolify
```

#### synonymas
入力した単語の類語を検索する
- [Big Huge Thesaurus](https://words.bighugelabs.com/)のAPI keyが必要
```
$ echo export BHT_APIKEY="Big Huge Thesaurus API Key" >> ~/.bash_profile // bashの場合。""不要
$ source ~/.bash_profile
$ cd $HOME/go/src/commandline_tool_for_domain_research/synonyms
$ go build -o synonyms
$ ./synonyms
```

#### available
入力したdomainが利用可能かwho is serverに問い合わせる
TLDは問い合わせ先serverの都合上, 対応しているのはnet comのみ
```
$ cd $HOME/go/src/commandline_tool_for_domain_research/available
$ go build -o available
$ ./available
```

### domainfinder
上記の5つを統合したもの  
入力から以下の順に実行した結果が出力される 
1. synonyms
2. sprinkle
3. coolify
4. domainify
5. available
```
$ cd $HOME/go/src/commandline_tool_for_domain_research/domainfinder
$ chmod 755 build.sh
$ ./build.sh
$ go build -o domainfinder
$ ./domainfinder
```