<script src="https://cdn.jsdelivr.net/npm/tify@0.27.0/dist/tify.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/list.js/2.3.1/list.min.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/tify@0.27.0/dist/tify.css">

# N図書館のページ

![ダウンロード](https://user-images.githubusercontent.com/47239711/188251983-518c8c33-50be-4f01-b588-0da5cc19aa48.png)

## お知らせ

 - 練習用のサイトです 
 - 新着図書が入りました（2022年9月2日）
 - 出来てる？

<div id="books">
  <input class="search" placeholder="検索" />
  <button class="sort" data-sort="title">
    タイトルで並べ替え
  </button>
  <ul class="list">
    <!-- _data フォルダの books.csv からデータを取り出す -->
    {% for book in site.data.books %}
      <li>
        <!-- books.csv の title 列、 url 列をリンク先に設定、著者も追加 -->
        <p class="title"><a href="{{ book.url }}">{{ book.title }}</a> <i>{{ book.author }}</i></p>
      </li>
    {% endfor %}
  </ul>
</div>

<script>
var options = {
    valueNames: [ 'title' ]
};

var userList = new List('books', options);
</script>
