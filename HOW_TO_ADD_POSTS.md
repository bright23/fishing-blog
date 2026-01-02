# 📝 ブログ記事の追加方法

## 🌐 公開記事（public）

### 手順
1. `/public` フォルダに新しいHTMLファイルを作成
2. 以下のテンプレートをコピーして使用
3. メインページの `index.html` にブログカードを追加

### HTMLテンプレート

```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>記事タイトル - さなか釣りブログ</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Hiragino Sans', 'Hiragino Kaku Gothic ProN', 'Yu Gothic', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            padding: 40px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .back-link {
            display: inline-block;
            margin-bottom: 30px;
            color: #667eea;
            text-decoration: none;
            padding: 10px 20px;
            background: rgba(102, 126, 234, 0.1);
            border-radius: 20px;
            transition: all 0.3s ease;
        }

        .back-link:hover {
            background: rgba(102, 126, 234, 0.2);
            transform: translateX(-5px);
        }

        .blog-header {
            margin-bottom: 30px;
            text-align: center;
        }

        .blog-date {
            color: #999;
            font-size: 0.9em;
            margin-bottom: 10px;
        }

        .blog-title {
            font-size: 2.5em;
            color: #333;
            margin-bottom: 20px;
            font-weight: bold;
        }

        .blog-image {
            width: 100%;
            height: 300px;
            background: linear-gradient(135deg, #a8edea 0%, #fed6e3 100%);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6em;
            margin-bottom: 30px;
        }

        .blog-content {
            color: #444;
            line-height: 1.8;
            font-size: 1.1em;
        }

        .blog-content h2 {
            color: #667eea;
            margin: 30px 0 15px 0;
            font-size: 1.5em;
        }

        .blog-content p {
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <a href="../index.html" class="back-link">← ブログ一覧に戻る</a>
        
        <div class="blog-header">
            <div class="blog-date">YYYY年MM月DD日</div>
            <h1 class="blog-title">記事タイトル</h1>
            <div class="blog-image">🎣</div>
        </div>

        <div class="blog-content">
            <p>記事の内容をここに書きます。</p>
            
            <h2>見出し</h2>
            <p>内容...</p>
        </div>
    </div>
</body>
</html>
```

### メインページへの追加

`index.html` の `<div class="blog-grid" id="blogGrid">` 内に以下を追加：

```html
<div class="blog-card">
    <div class="blog-image">🎣</div>
    <div class="blog-content">
        <div class="blog-date">日付を記入</div>
        <h2 class="blog-title">タイトル</h2>
        <p class="blog-excerpt">記事の抜粋...</p>
        <a href="public/ファイル名.html" class="read-more">続きを読む →</a>
    </div>
</div>
```

## 🔒 非公開記事（private）

### 手順
1. `/private` フォルダに新しいファイルを作成
2. MarkdownまたはHTMLで記事を作成
3. 下書きや個人的なメモとして使用

### Markdownテンプレート

```markdown
# 記事タイトル

**日付**: YYYY年MM月DD日  
**ステータス**: 下書き / レビュー中 / 完了  
**公開予定**: YYYY年MM月DD日  

## 概要
記事の概要をここに書きます。

## 本文
記事の内容をここに書きます。

### 見出し
内容...

## 画像
- 必要な画像: 
- 撮影予定: 

## TODO
- [ ] 内容の追加
- [ ] 画像の準備
- [ ] レビュー
- [ ] 公開
```

## 🖼️ 画像の追加方法

### 絵文字を使用
```html
<div class="blog-image">🎣</div>
```

### 実際の画像を使用
```html
<div class="blog-image" style="background-image: url('../images/画像ファイル名.jpg'); background-size: cover; background-position: center;"></div>
```

## 📁 ファイル命名規則

### 公開記事
- `YYYY-MM-DD-記事名.html` （例: `2024-12-25-first-fishing.html`）

### 非公開記事  
- `YYYY-MM-DD-記事名-draft.md` （例: `2024-12-25-new-post-draft.md`）

## 🚀 公開手順

1. **private** フォルダで記事を作成・編集
2. 内容が完成したら **public** フォルダに移動
3. Markdown → HTML に変換
4. `index.html` にブログカードを追加
5. 動作確認して公開完了

---

*このファイルは記事作成の参考用です。新しい機能や改善があれば随時更新してください。*