# Crypto-wallet-address-generator
## Генератор криптокошелька с определенными символами в начале и конце адреса

## Алгоритм генерации адреса btc или eth по заданным паттернам:
- Генерируется приватный ключ случайным образом.
- На основе приватного ключа вычисляется публичный ключ.
- Из публичного ключа генерируется адрес криптокошелька.
- Проверяется, соответствует ли адрес заданным требованиям.
- Если не соответствует, повторяем процесс.


🔑 Создание Bitcoin-кошелька
Bitcoin использует ECDSA, SHA-256 и RIPEMD-160 для создания адресов.
os.urandom(32) — генерирует случайный приватный ключ.
SigningKey.from_string() — создает приватный ключ с использованием кривой SECP256k1.
Хэширование: SHA-256 + RIPEMD-160.
Base58 — используется для представления адреса в удобочитаемом виде.

Функция для генерации Bitcoin-адреса возвращает Bitcoin-адрес и приватный ключ. Эти данные позволяют использовать кошелек для отправки, получения средств и управления средствами. В Bitcoin регистрация кошелька не требуется. Адрес автоматически становится доступным для использования в сети, как только вы совершаете транзакцию с этим адресом.


🔑 Создание Ethereum-кошелька
Ethereum использует алгоритмы ECDSA и Keccak-256 для генерации публичного ключа и адреса.
os.urandom(32) — генерирует 32 случайных байта для приватного ключа.
keys.PrivateKey() — создаёт объект приватного ключа.
keccak() — хэширует публичный ключ, и из него берутся последние 20 байт для адреса.
to_checksum_address() — возвращает адрес в формате с контрольной суммой.




## Важно!
Производительность: Чем больше символов в начале или конце адреса, тем дольше будет идти генерация.
Безопасность: Избегайте утечек приватных ключей.
Коллизии: Вероятность генерации двух одинаковых адресов крайне мала, но не исключена.
