# PHP App ① レビュー

## 全般

### 以下のaタグのリンクを押下した際にedit.phpの$_GETにどんな値が格納されるか説明してください。

```html
<a href="edit.php?todo_id=123&todo_content=焼肉">更新</a>
```
$_GETの値は連想配列のtodo_id->123とtodo_content->焼肉が入ります。

### 以下のフォームの送信ボタンを押下した際にstore.phpの$_POSTにどんな値が格納されるか説明してください。

```html
<form action="store.php" method="post">
    <input type="text" name="id" value="123">
		<textarea　name="content">焼肉</textarea>
    <button type="submit">送信</button>
</form>
```
$_POSTは連想配列で、キーはname="id" バリューはvalue="123"
$_POSTの'id'には "123" が格納され、$_POST'content'には "焼肉" が格納される。

### `require_once()` は何のために記述しているか説明してください。
例えば、require_once('config.php') と記述することにより、config.phpを読み込み、中に記載あるものが使用できる。

### `savePostedData($post)`は何をしているか説明してください。
savePostedData($post) は、ユーザーのメニュー選択に応じてTODOデータの作成や更新の処理を振り分ける関数です。

### `header('location: ./index.php')`は何をしているか説明してください。
index.php(最初にアクセスするページ)に移動させている。

### `getRefererPath()`は何をしているか説明してください。
URLからパス情報を取得している。

### `connectPdo()` の返り値は何か、またこの記述は何をするための記述か説明してください。
返り値はPDOインスタンスで、DBに接続するための記述です。

### `try catch`とは何か説明してください。
エラーや例外処理に対する処理のこと。

### Pdoクラスをインスタンス化する際に`try catch`が必要な理由を説明してください。
エラーや例外処理が発生するたびに、アプリが停止したりクラッシュするのを防ぐため。

## 新規作成

### `createTodoData($post)`は何をしているか説明してください。
functions.phpからフォームに入力した値を受け取り、todosテーブルに保存します。
最後に最初にアクセスするページに戻ります。

## 一覧

### `getTodoList()`の返り値について説明してください。
返り値はtodosテーブルの保存されているデータ。削除されていないレコードのみを取得しています。

### `<?= ?>`は何の省略形か説明してください。
これは echo の省略形です。

<?php echo $todo['id']; ?>

//上下は同じ意味

<?= $todo['id']; ?>
上のechoと書いてある書き方よりも下の方がシンプルで読みやすいですよね。
こちらもよく使う記法になります。HTML・PHPが混在しているときで、PHPタグ内でechoするときはこの書き方で記述するようにしてください。
## 更新

### `getSelectedTodo($_GET['id'])`の返り値は何か、またなぜ`$_GET['id']` を引数に渡すのか説明してください。

### `updateTodoData($post)`は何をしているか説明してください。

## 削除

### `deleteTodoData($id)`は何をしているか説明してください。

### `deleted_at`を現在時刻で更新すると一覧画面からToDoが非表示になる理由を説明してください。

### 今回のように実際のデータを削除せずに非表示にすることで削除されたように扱うことを〇〇削除というか。

### 実際にデータを削除することを〇〇削除というか。

### 前問のそれぞれの削除のメリット・デメリットについて説明してください。
