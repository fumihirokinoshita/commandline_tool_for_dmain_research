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
入力した単語の後ろにTLDを追加する
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
- Big Huge ThesaurusのAPI keyが必要
```
$ export BHT_APIKEY="Big Huge Thesaurus API Key"
$ cd $HOME/go/src/commandline_tool_for_domain_research/synonyms
$ go build -o synonyms
$ ./synonyms
```