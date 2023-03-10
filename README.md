# HBSPC-1

Lenguages: [English](#English) | [Русский](#Русский)

# English

**Table of contents:**
* [About](#About)
* [Risks and Recommendations](#Risks-and-Recommendations)

## About

**HBSPC-1** *(Hashing-based Secure Password Calculation 1st Gen)* is a hashing-based algorithm for deterministic generation of secure passwords using user passkeys.
This algorithm is designed to solve the problem of creating, remembering and storing strong passwords.

The user doesn't need to remember or save a password, it is enough for him to remember the passkey (phrase), which can be quite simple. 
The passkey can be a string of any length. The algorithm calculates a secure password 32 characters long that contains upper and lower 
case letters (A-F), numbers (0-9), symbols.

Example:

| Passkey    | Password                           |
| ---------- | ---------------------------------- |
| password   | `266B:ea21=fCa3+B9f1?926D>e87c^61` |
| qwerty     | `5Ff^6Fe17F8{a3628Cb*22a3134%5C98` |
| 123        | `6f31\1C4Fb7b'8Ae934d}19d1935(1E5` |
| bob        | `d19d>378ec\c0Eae]7f1ce\306d5^868` |
| 01.01.1970 | `0F85"B8D4/a951_680a/3CdE^Ad27=e7` |

> **WARNING!** Do not use very simple passkeys!

The algorithm has an avalanche effect due to which even a slight change in the passkey can completely change the result.

Example:

| Passkey    | Password                           |
| ---------- | ---------------------------------- |
| secretkey  | `B0e}4cE29:23Cb1+4a0d4}fb267"51D2` |
| secretKey  | `7bc8$99B40)C462D<9f0e7*5055D#636` |
| secret key | `<8e9251}199B09^B45f55(e5504F%D55` |

> The algorithm is case and space sensitive!

## Risks and Recommendations

The main risk of using HBSPC-1 is the possibility for an attacker to enumerate simple and popular passkeys and calculate passwords. 
To avoid password compromise, **do not use too short and simple passkeys!**

**Do not store passkeys in plain text!** If there is a need to save the passkey, use encryption (for example, AES).

**Do not use identical passkeys** for passwords from different services (accounts)!

**Use 2-Step Verification** on all services if possible!

# Русский

**Содержание:**
* [Описание](#Описание)
* [Риски и Рекомендации](#Риски-и-Рекомендации)

## Описание

**HBSPC-1** *(Hashing-based Secure Password Calculation 1st Gen)* — это алгоритм для детерминированной генерации паролей на основе пользовательских ключей.
Данный алгоритм призван решить проблему создания, запоминания и хранения сложных паролей.

Пользователю не нужно запоминать или сохранять где-либо сложный пароль, ему достаточно запомнить ключ (фразу), который может быть довольно простым. 
Ключом может служить строка произвольной длины. Алгоритм вычисляет из ключа безопасный 32-значный пароль, который содержит буквы верхнего и нижнего 
регистра (A-F), цифры (0-9), спецсимволы.

Пример:

| Ключ       | Пароль                             |
| ---------- | ---------------------------------- |
| password   | `266B:ea21=fCa3+B9f1?926D>e87c^61` |
| qwerty     | `5Ff^6Fe17F8{a3628Cb*22a3134%5C98` |
| 123        | `6f31\1C4Fb7b'8Ae934d}19d1935(1E5` |
| bob        | `d19d>378ec\c0Eae]7f1ce\306d5^868` |
| 01.01.1970 | `0F85"B8D4/a951_680a/3CdE^Ad27=e7` |

> **ВНИМАНИЕ!** Не используйте слишком простые ключи!

Алгоритм обладает лавинным эффектом, благодаря чему даже незначительное изменение ключа способно полностью изменить результат.

Пример:

| Ключ       | Пароль                             |
| ---------- | ---------------------------------- |
| secretkey  | `B0e}4cE29:23Cb1+4a0d4}fb267"51D2` |
| secretKey  | `7bc8$99B40)C462D<9f0e7*5055D#636` |
| secret key | `<8e9251}199B09^B45f55(e5504F%D55` |

> Алгоритм чувствителен к регистру и пробелам!

## Риски и Рекомендации

Основным риском использования HBSPC-1 является возможность перебора злоумышленником простых и популярных ключей и вычисление из них соответствующих паролей. 
Во избежание компрометации пароля **не используйте слишком короткие и простые ключи!**

**Не храните ключи в открытом виде!** Если есть необходимость сохранить ключ, используйте шифрование (например, AES).

**Не используйте идентичные ключи** для паролей от разных сервисов (аккаунтов)!

**Используйте двухэтапную аутентификацию** во всех сервисах, если есть возможность!
