# calendar-share

Google カレンダーの予定を、Google アカウントなしで閲覧できる公開ページです。  
GitHub Pages でホスティングしているため、PC の電源に関わらず常時アクセス可能です。

## 機能

- 月表示・一覧表示の切り替え
- イベントをクリックすると開始・終了時刻と場所を表示
- スマートフォン対応

## セットアップ

### 1. Google Calendar API キーの取得

1. [Google Cloud Console](https://console.cloud.google.com/) にアクセスしてプロジェクトを作成
2. 「API とサービス」→「ライブラリ」→「Google Calendar API」を有効化
3. 「API とサービス」→「認証情報」→「認証情報を作成」→「API キー」をクリック
4. 作成された API キーをコピー
5. （推奨）API キーの制限で「HTTP リファラー」に `https://mogw4086.github.io/*` を設定

### 2. API キーとカレンダー ID を設定

`index.html` の以下の2行を編集します。

```javascript
const GOOGLE_CALENDAR_API_KEY = 'YOUR_GOOGLE_CALENDAR_API_KEY';
const CALENDAR_ID = 'YOUR_CALENDAR_ID@group.calendar.google.com';
```

- `YOUR_GOOGLE_CALENDAR_API_KEY` → 手順1で取得した API キーに置き換える
- `YOUR_CALENDAR_ID@group.calendar.google.com` → Google カレンダーの設定画面「カレンダーの統合」に記載されているカレンダー ID に置き換える

### 3. GitHub Pages で公開

`main` ブランチにプッシュすると自動で反映されます。

**公開 URL:** `https://mogw4086.github.io/calendar-share/`

## 予定の追加・管理

Google カレンダーの「公開用カレンダー」に予定を追加するだけで、ページに自動反映されます。  
非公開にしたい予定は、その予定の設定で「非公開」を選択してください。
