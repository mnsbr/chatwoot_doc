# Cara Mengaktifkan Validasi Identitas di Katalis

Validasi identitas membantu memastikan bahwa percakapan antara pelanggan dan agen dukungan Anda bersifat pribadi. Ini juga membantu mencegah peniruan identitas.

Validasi identitas bisa diaktifkan dengan menghasilkan HMAC.

Key yang digunakan untuk menghasilkan HMAC untuk setiap web widget berbeda dan bisa disalin dari Inboxes → Settings → Configuration → Identity Validation → Salin token yang ditampilkan di sana.

Anda bisa menghasilkan HMAC dalam berbagai bahasa pemrograman, seperti yang ditunjukkan di bawah.

## Menghasilkan HMAC

### PHP
```php
<?php
$key = '<webwidget-hmac-token>';
$message = '<identifier>';
$identifier_hash = hash_hmac('sha256', $message, $key);
?>
```

### Javascript (Node.js)
```javascript
const crypto = require('crypto');
const key = '<webwidget-hmac-token>';
const message = '<identifier>';
const hash = crypto.createHmac('sha256', key).update(message).digest('hex');
```

### Ruby
```ruby
require 'openssl'
require 'base64'
key = '<webwidget-hmac-token>'
message = '<identifier>'
OpenSSL::HMAC.hexdigest('sha256', key, message)
```

### Elixir
```elixir
key = '<webwidget-hmac-token>'
message = '<identifier>'
signature = :crypto.hmac(:sha256, key, message)
Base.encode16(signature, case: :lower)
```

### Golang
```go
package main
import (
    "crypto/hmac"
    "crypto/sha256"
    "encoding/hex"
)
func main() {
  secret := []byte("<webwidget-hmac-token>")
  message := []byte("<identifier>")
  hash := hmac.New(sha256.New, secret)
  hash.Write(message)
  hex.EncodeToString(hash.Sum(nil))
}
```

### Python
```python
import hashlib
import hmac
secret = bytes('<webwidget-hmac-token>', 'utf-8')
message = bytes('<identifier>', 'utf-8')
hash = hmac.new(secret, message, hashlib.sha256)
hash.hexdigest()
```
