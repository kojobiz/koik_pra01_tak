## icon
FontAwasome
https://fontawesome.com/search?q=calender&o=r
circle-user https://fontawesome.com/search?q=user%20circle&o=r

## svgファイル処理
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">⭐️<!--!Font Awesome Free 6.5.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->⭐️<path d="M48 64C21.5 64 0 85.5 0 112c0 15.1 7.1 29.3 19.2 38.4L236.8 313.6c11.4 8.5 27 8.5 38.4 0L492.8 150.4c12.1-9.1 19.2-23.3 19.2-38.4c0-26.5-21.5-48-48-48H48zM0 176V384c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V176L294.4 339.2c-22.8 17.1-54 17.1-76.8 0L0 176z"/></svg>

となっているので、⭐️から⭐️の間を削除し<path>を入れ子にする
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M48 64C21.5 64 0 85.5 0 112c0 15.1 7.1 29.3 19.2 38.4L236.8 313.6c11.4 8.5 27 8.5 38.4 0L492.8 150.4c12.1-9.1 19.2-23.3 19.2-38.4c0-26.5-21.5-48-48-48H48zM0 176V384c0 35.3 28.7 64 64 64H448c35.3 0 64-28.7 64-64V176L294.4 339.2c-22.8 17.1-54 17.1-76.8 0L0 176z"/>
</svg>
path dの手前にfill
svgの中にwidth,height, aria-hidden, focusable, data-prefix(fontawasomeの時だけ)を入れ込んでOK、参考↓
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512" width="35" height="26" class="icon" aria-hidden="true" focusable="false" data-prefix="fas" ><path fill="#fff" d="M128 0c17.7 0 32 14.3 32 32V64H288V32c0-

## sassのカラー登録や、svgfillでの指定方法
カラーを変数にする
$color-primary: #3498db;
// svgでfillで使用したいときは変数にクラスを再設定する必要あり
.color-primary {
    fill:$color-primary;
}のように指定する
htmlでは-- pathのfillにカラー指定をせず、svgにsassコンパイルのcolor-primaryを指定する方法 <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" width="26" height="26" class="icon color-primary" aria-hidden="true" focusable="false" data-prefix="fas"><path d="M406.5 399.6C387.4 352.9 341.5 320 288 320H224c-53.5 0-99.4 32.9-118.5 79.6C69.9 362.2 48 311.7 48 256C48 141.1 141.1 48 256 48s208 93.1 208 208c0 55.7-21.9 106.2-57.5 143.6zm-40.1 32.7C334.4 452.4 296.6 464 256 464s-78.4-11.6-110.5-31.7c7.3-36.7 39.7-64.3 78.5-64.3h64c38.8 0 71.2 27.6 78.5 64.3zM256 512A256 256 0 1 0 256 0a256 256 0 1 0 0 512zm0-272a40 40 0 1 1 0-80 40 40 0 1 1 0 80zm-88-40a88 88 0 1 0 176 0 88 88 0 1 0 -176 0z"></svg>

## 合体処理1
<svg xmlns="http://www.w3.org/2000/svg" width="43.238" height="26.635" viewBox="0 0 43.238 26.635" class="icon"><g fill="#fff" clip-path="url(#a)"><path d="M13.318 6.417a6.9 6.9 0 0 0-5.173 11.46 4.814 4.814 0 0 1 4.367-2.787h1.612a4.814 4.814 0 0 1 4.367 2.787 6.9 6.9 0 0 0-5.173-11.46m0 7.4a2.569 2.569 0 1 1 2.569-2.569 2.569 2.569 0 0 1-2.569 2.569"/><path d="M39.779-.001H3.459A3.463 3.463 0 0 0 0 3.459v19.716a3.463 3.463 0 0 0 3.459 3.459h36.32a3.463 3.463 0 0 0 3.459-3.459V3.459a3.463 3.463 0 0 0-3.459-3.46M13.317 21.731a8.414 8.414 0 1 1 8.414-8.414 8.423 8.423 0 0 1-8.414 8.414m18.733-1.458h-6.189a.757.757 0 0 1 0-1.513h6.189a.757.757 0 1 1 0 1.513m5.508-4.133h-11.7a.757.757 0 0 1 0-1.513h11.7a.757.757 0 0 1 0 1.513m0-4.133h-11.7a.757.757 0 0 1 0-1.513h11.7a.757.757 0 0 1 0 1.513m0-4.133H32.05a.757.757 0 1 1 0-1.513h5.508a.757.757 0 0 1 0 1.513"/></g></svg>

## 合体処理２
<svg xmlns="http://www.w3.org/2000/svg" width="24.6" height="18.6" viewBox="0 0 24.68 18.65"><g style="fill:#2c73c6; stroke-width:0"><path d="M4.44 0c.59.01 1.83.25 5.33.88 3.85.7 5.01.93 5.18 1.02.36.22.65.54.82.93.15.42.15.87 0 1.28-.06.16-.68 1.32-1.39 2.59S13.1 9.02 13.1 9.03s2.16 1.21 4.79 2.66c.76.42 1.46.81 2.1 1.16a9.24 9.24 0 0 0-2.22-.27c-.85-.05-1.7.06-2.51.33-2.41.72-4.77 2-7.24 2.71-2.49.72-2.45-1.18-2.18-2.03.24-.47.29-.61 2.08-3.77 1.53-2.7 2.73-4.94 2.72-4.94s-1.45-.27-3.2-.59-3.3-.62-3.43-.66c-.52-.17-.95-.54-1.18-1.03-.11-.24-.16-.5-.13-.76-.03-.26.01-.52.13-.76.19-.4.51-.72.9-.92.23-.11.47-.17.71-.16Zm-.76 5.78c1.89 0 3.42 1.53 3.42 3.42s-1.53 3.42-3.42 3.42S.25 11.09.25 9.2s1.53-3.42 3.42-3.42m14.06 7.54c1.75-.03 3.46.49 4.9 1.48.71.54 1.35 1.17 1.89 1.88.3.49.14 1.13-.35 1.42-.19.11-.41.17-.62.15-.66 0-.9-.51-1.12-.74a6.387 6.387 0 0 0-4.75-2.07c-3.18.09-6.46 2.78-10.1 3.19-2.28.25-5.89-.68-7.27-3.03-.91-1.49.34-2.57 1.46-1.43a6.533 6.533 0 0 0 5.37 2.36c2.84-.21 5.4-2.06 8.07-2.86.81-.27 1.66-.38 2.51-.32Z"/></g></svg>

## スクロール可能の可視化
スクロールヒントサイトページ　https://appleple.github.io/scroll-hint/
・headerに　<link rel="stylesheet" href="https://unpkg.com/scroll-hint@latest/css/scroll-hint.css">
<script src="https://unpkg.com/scroll-hint@latest/js/scroll-hint.min.js"></script>を入力して
<div class="js-scrollable">
        <table>
            <thead>
                <tr>
                    <th>title1</th>
                    <th>title2</th>
                    <th>title3i</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>Lorem ipsum dolor sit amet consectetur adipisicing elit. Deleniti, eaque recusandae corrupti, ex modi ceat recusandae minus, aut est assumenda.</td>
                    <td>id reprehenderit dolores molestium perferendis enim, minus cumque itaque aliquam.
                    </td>
                    <td>as voluptates dolor officia ipsam. Quisquam accusanti
                    </td>
                </tr>
            </tbody>
        </table>
    </div>で囲んで <script>
        new ScrollHint('.js-scrollable', {
            scrollHintIconAppendClass: 'scroll-hint-icon-white',
            applyToParents: true,
            i18n: {
                scrollable: 'スクロールできます'
            }
    });
    </script>で処理する