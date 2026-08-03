# TECMOPIA Stamp Rally / GitHub Ready

## Files
- `index.html` : GitHub Pages / static hosting ready main file
- `assets/medal_50.webp`
- `assets/medal_30.webp`
- `assets/medal_10.webp`

## Already integrated
- B1ミニクレ / 3Fテクモピア のスタンプ画像は **HTML内に埋め込み済み** です。
- メダルクーポン画像は `assets/*.webp` を参照するように変更済みです。
- 既存の古いPNGパスが localStorage に残っていても、自動で webp に置換されます。

## Important
このHTMLはヘッダーロゴとして **`main.png`** を参照しています。
もしGitHubリポジトリに `main.png` がまだ無い場合は、
`index.html` と同じ階層に `main.png` を置いてください。

## Image insertion points in code
### 1. Header logo
```html
<img src="main.png" alt="TECMOPIA">
```

### 2. Coupon image assignment (gacha result)
`index.html` 内の `couponsToPush.push(...)` で下記3枚を使っています。
- `assets/medal_50.webp`
- `assets/medal_30.webp`
- `assets/medal_10.webp`

### 3. Coupon modal rendering
`openUseModal()` 内で `c.img` を `<img>` として表示しています。

## Recommended GitHub structure
```text
/index.html
/main.png
/assets/medal_50.webp
/assets/medal_30.webp
/assets/medal_10.webp
```
