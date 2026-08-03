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


## ガチャ確率（7等50％版）
抽選は140口の整数方式です。7等を70口＝50％に固定し、1〜6等は以前の比率 `1:9:3:20:15:22` を維持しています。

| 等級 | 口数 | 確率 |
|---|---:|---:|
| 1等 | 1 / 140 | 約0.7143％ |
| 2等 | 9 / 140 | 約6.4286％ |
| 3等 | 3 / 140 | 約2.1429％ |
| 4等 | 20 / 140 | 約14.2857％ |
| 5等 | 15 / 140 | 約10.7143％ |
| 6等 | 22 / 140 | 約15.7143％ |
| 7等 | 70 / 140 | 50％ |


## Stamp UI updates
- Stamp images inside the progress cards are displayed larger.
- The stamp-get popup now also shows the stamp image that was acquired.


## Deluxe stamp popup
- Gold double-frame and stronger shadow around the acquired stamp.
- Impact-style stamp animation, rotating rays, sparkle burst, confetti, and vibration.
- Stamp-complete popup uses a stronger celebration effect.


## Final clear screen update
- The final CLEAR screen now shows `assets/clear_finish.webp` instead of the 🎉 emoji.
- Message updated to: 「本日の探検は終了！また遊んでね！」


## Final clear sparkle update
- Added sparkle effects around the final clear image.
- Upgraded the CLEAR! title with glow, outline, bounce, and shiny gold styling.


## In-app camera anti-fraud update
- QR stamp acquisition now requires a short-lived, one-use ticket created only by the website's built-in camera scanner.
- Opening a QR URL with `?id=1` or `?id=2` from the phone's normal camera no longer grants a stamp.
- External scan query parameters are removed immediately and a guidance notice is displayed.
- Existing printed QR URLs remain usable when scanned from the in-site scanner.

> This is a client-side protection for a static GitHub Pages site. It blocks ordinary external-camera scans, but a fully tamper-resistant system would require server-side verification.
