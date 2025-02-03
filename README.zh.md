# PD\Session

> PD\Session 是一個靈活的 PHP 工作階段管理器，支援 Redis 儲存並具有檔案系統備用功能。提供安全的工作階段處理。

![tag](https://img.shields.io/badge/tag-PHP%20Library-bb4444)
![size](https://img.shields.io/github/size/pardnchiu/PHP-Session/src/Session.php)  
![version](https://img.shields.io/packagist/v/pardnchiu/session)
![download](https://img.shields.io/packagist/dm/pardnchiu/session)

## 特色功能

- 雙重儲存支援（Redis / 檔案系統）
- 自動備用機制
- 工作階段安全強化
- 內建工作階段生命週期管理
- 工作階段 ID 重新產生
- 建立時間追蹤

## 安全功能

- 7 天工作階段有效期限
- 自動垃圾回收
- 支援工作階段 ID 重新產生
- 安全儲存處理
- 系統彈性備用機制

## 相依套件

- `pardnchiu/redis` - Redis 快取支援（選用）
- `/storage/sessions` - 儲存目錄需要寫入權限

## 使用方式

### 安裝

```shell
composer require pardnchiu/session
```

```php
// 使用 Redis 支援進行初始化
$redis = new PD\Redis();
$session = new PD\Session($redis);

// 基本工作階段操作
$session->set("user_id", 123);
$userId = $session->get("user_id");
$session->delete("user_id");

// 安全性操作
$session->regenerateId();   // 重新產生工作階段 ID
$session->destroy();        // 銷毀工作階段

// 工作階段資訊
$sessionId = $session->getId();
$createdTime = $session->getCreatedTime();

// 不使用 Redis 初始化（僅檔案系統）
$session = new PD\Session();
```

## 授權條款

此原始碼專案採用 [MIT](https://github.com/pardnchiu/PHP-Session/blob/main/LICENSE) 授權。

## 作者

<img src="https://avatars.githubusercontent.com/u/25631760" align="left" width="96" height="96" style="margin-right: 0.5rem;">

#### 邱敬幃 Pardn Chiu

<a href="mailto:dev@pardn.io" target="_blank">
 <img src="https://pardn.io/image/email.svg" width="48" height="48">
</a>
<a href="https://linkedin.com/in/pardnchiu" target="_blank">
 <img src="https://pardn.io/image/linkedin.svg" width="48" height="48">
</a>

---

©️ 2024 [邱敬幃 Pardn Chiu](https://pardn.io)