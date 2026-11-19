# suikouban

随口办（com.suikouban.app）的版本更新清单仓库。

`update.json` 是这个仓库唯一的用途：App 固定访问它的 raw 地址，每次发版只覆盖这一个文件的内容，URL 不变。

## 三个访问地址（App 依次尝试）

1. `https://raw.githubusercontent.com/cyccdma-jim/suikouban/main/update.json`（主）
2. `https://cdn.jsdelivr.net/gh/cyccdma-jim/suikouban@main/update.json`（镜像，国内更快）
3. CDN 清单（App 内置兜底，只在上面两个都拉不到时用）

## update.json 字段

| 字段 | 含义 |
|---|---|
| versionCode | 版本序号，比较大小用，必须逐版递增 |
| versionName | 显示给用户的版本号 |
| apkUrl | APK 直链，上传后填进来 |
| sha256 | APK 的 sha256，下载完用来校验，不对就不装 |
| changelog | 检查更新弹窗里显示的这版改动 |

## 发版三步

1. 编译签名出新 APK，上传拿直链
2. 改本仓库 `update.json` 的四个字段（versionCode、versionName、apkUrl、sha256、changelog）
3. 提交。旧版本点「检查更新」立刻就能看到新版
