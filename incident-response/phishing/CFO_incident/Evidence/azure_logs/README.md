## На Снимках экрана присутствуют события вида:
- `AuditSearchCreated` (для `liam.fray`)
- `PurviewSearchListViewed` (для `liam.fray`)
- `CaseSettingsViewed` / `StatisticsResultsViewed` (для `liam.fray`)

Это похоже на работу вокруг поисковых/комплаенс-операций (Purview / audit search).  
В атаке это может означать:
- злоумышленник (или злоупотребление привилегиями) пытается **искать и “выгружать”** контент через механизмы поиска/аудита
- либо это легитимный комплаенс-процесс (но тогда должны быть понятные роли/учётки и согласованное окно изменений)

### `Search` по Liam (разведка по почте)
На  Снимках экрана видно `Search` по `liam.fray@tempestasenergy.com`.

**Логика злоумышленника:**
- найти переписки с CFO/пенсионным фондом/контрагентами
- вытащить “нить” для подмены переписки и BEC

### `MailItemsAccessed` по Liam (доступ к содержимому)
На Снимках экрана есть `MailItemsAccessed` по `liam.fray@tempestasenergy.com`.
`MailItemsAccessed` - не просто “интересовались”, а **открывали/читали** письма.

### Переход к Becky (финансовая цель)
Дальше на Снимок экрана (20) появляется активность уже вокруг `becky.loray@tempestasenergy.com`:
- `UserLoggedIn` (Becky)
- `TeamsSessionStarted` (Becky)
- `MailItemsAccessed` (Becky)
- встречается `SharingInheritanceBroken` (Becky) — потенциальный признак изменения наследования/шаринга (требует уточнения в JSON)

### `Set-Mailbox` под `NT AUTHORITY\SYSTEM` (изменения конфигурации)
На Снимках экрана присутствуют множественные `Set-Mailbox` от `NT AUTHORITY\SYSTEM`.
Если `Set-Mailbox` встречается в окне, где уже есть `Search` и `MailItemsAccessed`, то это может быть закрепление (persistence) или подготовка к длительному доступу.
