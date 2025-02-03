# PD\Session

> PD\Session is a flexible PHP session manager with Redis support and filesystem fallback. Provides secure session handling.

![tag](https://img.shields.io/badge/tag-PHP%20Library-bb4444)
![size](https://img.shields.io/github/size/pardnchiu/PHP-Session/src/Session.php)<br>
![version](https://img.shields.io/packagist/v/pardnchiu/session)
![download](https://img.shields.io/packagist/dm/pardnchiu/session)

## Features

- Dual storage support (Redis / Filesystem)
- Automatic fallback mechanism
- Session security enhancements
- Built-in session lifetime management
- Session ID regeneration
- Creation time tracking

## Security Features

- 7-day session lifetime
- Automatic garbage collection
- Session ID regeneration support
- Secure storage handling
- System resilience fallback mechanism

## Dependencies

- `pardnchiu/redis` - For Redis caching support (optional)
- `/storage/sessions` - Write permission required for storage directory

## How to Use

### Installation

```shell
composer require pardnchiu/session
```

```php
// Initialize with Redis support
$redis = new PD\Redis();
$session = new PD\Session($redis);

// Basic session operations
$session->set("user_id", 123);
$userId = $session->get("user_id");
$session->delete("user_id");

// Security operations
$session->regenerateId();   // Regenerate session ID
$session->destroy();        // Destroy session

// Session information
$sessionId = $session->getId();
$createdTime = $session->getCreatedTime();

// Initialize without Redis (filesystem only)
$session = new PD\Session();
```

## License

This source code project is licensed under the [MIT](https://github.com/pardnchiu/PHP-Session/blob/main/LICENSE) license.

## Creator

<img src="https://avatars.githubusercontent.com/u/25631760" align="left" width="96" height="96" style="margin-right: 0.5rem;">

#### Pardn Chiu

<a href="mailto:dev@pardn.io" target="_blank">
 <img src="https://pardn.io/image/email.svg" width="48" height="48">
</a>
<a href="https://linkedin.com/in/pardnchiu" target="_blank">
 <img src="https://pardn.io/image/linkedin.svg" width="48" height="48">
</a>

---

©️ 2024 [Pardn Chiu](https://pardn.io)