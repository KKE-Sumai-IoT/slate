
<p align="center">
  <img src="https://raw.githubusercontent.com/slatedocs/img/main/logo-slate.png" alt="Slate: API Documentation Generator" width="226">
  <br>
  <a href="https://github.com/slatedocs/slate/actions?query=workflow%3ABuild+branch%3Amain"><img src="https://github.com/slatedocs/slate/workflows/Build/badge.svg?branch=main" alt="Build Status"></a>
  <a href="https://hub.docker.com/r/slatedocs/slate"><img src="https://img.shields.io/docker/v/slatedocs/slate?sort=semver" alt="Docker Version" /></a>
</p>

<p align="center">Slate helps you create beautiful, intelligent, responsive API documentation.</p>

<p align="center"><img src="https://raw.githubusercontent.com/slatedocs/img/main/screenshot-slate.png" width=700 alt="Screenshot of Example Documentation created with Slate"></p>

<p align="center"><em>The example above was created with Slate. Check it out at <a href="https://slatedocs.github.io/slate">slatedocs.github.io/slate</a>.</em></p>

How to start in ローカル
------------------------------
* UIでdockerアプリの起動
* ターミナル　docker run --rm --name slate -v $(pwd)/build:/srv/slate/build -v $(pwd)/source:/srv/slate/source slatedocs/slate build
* ターミナル　docker run --rm --name slate -p 4567:4567 -v $(pwd)/source:/srv/slate/source slatedocs/slate serve
* ブラウザで　http://127.0.0.1:4567/ または　http://127.0.0.1:4567/__middleman にアクセス。
    
* 通常と異なるところ
    APIの複数ページを準備。
    includeファイルをerb化。(css記載のため)
    layoutファイルを、ファイルパスにより切り替え。*article*のあるものは、記事用にscreen_article.css.scssと_variables_article.scssを適用。
        メインコンテンツがワイドレイアウト、文字ベースを大きく、背景色を白に、他デザイン修正。
        
    画像は、個別に埋め込む場合は、先にHubSpot上にファイルアップロードして絶対パスでリンクする。

How to publish in web（ハブスポット利用）
------------------------------
* Hubspotへのリリース
	ページの更新
	- ローカルでslateで作成したページを表示。（http://127.0.0.1:4567/　ブラウザで挙動確認はchromeで実施している）
	- 右クリックでページのソースを表示する。そのままブラウザでソースコードを全コピー。(ダウンロードするとソースコード上の相対パスにファイル名等が混じってパスが崩れるので注意)
	- HubSpotの当該ページを開いて編集。htmlモジュールの内容を丸ごと差し替えて、Webページを更新（公開）
    htmlソースの更新
    アセットの更新
    - https://remotelock.kke.co.jp/hubfs/EBOOKS/API/confidential/apidoc_assets/にあるファイルをファイル置き換え。
    アセットの追加
    	HubSpot上の以下のパスにアップする。https://remotelock.kke.co.jp/hubfs/EBOOKS/API/confidential/apidoc_assets/　
    	リンク	https://app.hubspot.com/files/2864453/?sortDirection=descending&orderBy=updated&folderId=75963501905&archived=false
    	プロキシのリダイレクトで、slateの相対パスに合わせる。
	    	設定パス　http://remotelock.kke.co.jp/confi/remotelock-apidoc/
	    	設定画面　https://app.hubspot.com/settings/2864453/domains/url-redirects
    ページの新規作成
    	HubSpot上のランディングページとして作成する。
    	https://app.hubspot.com/website/2864453/pages/landing/12673079
        ページはいずれもパスワード付き。パスワード remotelock
        公開仕様書のトップパスは　　https://remotelock.kke.co.jp/confi/remotelock-apidoc/
		仕様書の追加ページパス　https://remotelock.kke.co.jp/confi/remotelock-apidoc/＊
		記事の公開パス　https://remotelock.kke.co.jp/confi/api-articles/＊


Features
------------

* **Clean, intuitive design** — With Slate, the description of your API is on the left side of your documentation, and all the code examples are on the right side. Inspired by [Stripe's](https://stripe.com/docs/api) and [PayPal's](https://developer.paypal.com/webapps/developer/docs/api/) API docs. Slate is responsive, so it looks great on tablets, phones, and even in print.

* **Everything on a single page** — Gone are the days when your users had to search through a million pages to find what they wanted. Slate puts the entire documentation on a single page. We haven't sacrificed linkability, though. As you scroll, your browser's hash will update to the nearest header, so linking to a particular point in the documentation is still natural and easy.

* **Slate is just Markdown** — When you write docs with Slate, you're just writing Markdown, which makes it simple to edit and understand. Everything is written in Markdown — even the code samples are just Markdown code blocks.

* **Write code samples in multiple languages** — If your API has bindings in multiple programming languages, you can easily put in tabs to switch between them. In your document, you'll distinguish different languages by specifying the language name at the top of each code block, just like with GitHub Flavored Markdown.

* **Out-of-the-box syntax highlighting** for [over 100 languages](https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers), no configuration required.

* **Automatic, smoothly scrolling table of contents** on the far left of the page. As you scroll, it displays your current position in the document. It's fast, too. We're using Slate at TripIt to build documentation for our new API, where our table of contents has over 180 entries. We've made sure that the performance remains excellent, even for larger documents.

* **Let your users update your documentation for you** — By default, your Slate-generated documentation is hosted in a public GitHub repository. Not only does this mean you get free hosting for your docs with GitHub Pages, but it also makes it simple for other developers to make pull requests to your docs if they find typos or other problems. Of course, if you don't want to use GitHub, you're also welcome to host your docs elsewhere.

* **RTL Support** Full right-to-left layout for RTL languages such as Arabic, Persian (Farsi), Hebrew etc.

Getting started with Slate is super easy! Simply press the green "use this template" button above and follow the instructions below. Or, if you'd like to check out what Slate is capable of, take a look at the [sample docs](https://slatedocs.github.io/slate/).

Getting Started with Slate
------------------------------

To get started with Slate, please check out the [Getting Started](https://github.com/slatedocs/slate/wiki#getting-started)
section in our [wiki](https://github.com/slatedocs/slate/wiki).

We support running Slate in three different ways:
* [Natively](https://github.com/slatedocs/slate/wiki/Using-Slate-Natively)
* [Using Vagrant](https://github.com/slatedocs/slate/wiki/Using-Slate-in-Vagrant)
* [Using Docker](https://github.com/slatedocs/slate/wiki/Using-Slate-in-Docker)


Companies Using Slate
---------------------------------

* [NASA](https://api.nasa.gov)
* [Sony](http://developers.cimediacloud.com)
* [Best Buy](https://bestbuyapis.github.io/api-documentation/)
* [Travis-CI](https://docs.travis-ci.com/api/)
* [Greenhouse](https://developers.greenhouse.io/harvest.html)
* [WooCommerce](http://woocommerce.github.io/woocommerce-rest-api-docs/)
* [Dwolla](https://docs.dwolla.com/)
* [Clearbit](https://clearbit.com/docs)
* [Coinbase](https://developers.coinbase.com/api)
* [Parrot Drones](http://developer.parrot.com/docs/bebop/)
* [CoinAPI](https://docs.coinapi.io/)

You can view more in [the list on the wiki](https://github.com/slatedocs/slate/wiki/Slate-in-the-Wild).

Questions? Need Help? Found a bug?
--------------------

If you've got questions about setup, deploying, special feature implementation in your fork, or just want to chat with the developer, please feel free to [start a thread in our Discussions tab](https://github.com/slatedocs/slate/discussions)!

Found a bug with upstream Slate? Go ahead and [submit an issue](https://github.com/slatedocs/slate/issues). And, of course, feel free to submit pull requests with bug fixes or changes to the `dev` branch.

Contributors
--------------------

Slate was built by [Robert Lord](https://lord.io) while at [TripIt](https://www.tripit.com/). The project is now maintained by [Matthew Peveler](https://github.com/MasterOdin) and [Mike Ralphson](https://github.com/MikeRalphson).

Thanks to the following people who have submitted major pull requests:

- [@chrissrogers](https://github.com/chrissrogers)
- [@bootstraponline](https://github.com/bootstraponline)
- [@realityking](https://github.com/realityking)
- [@cvkef](https://github.com/cvkef)

Also, thanks to [Sauce Labs](http://saucelabs.com) for sponsoring the development of the responsive styles.
