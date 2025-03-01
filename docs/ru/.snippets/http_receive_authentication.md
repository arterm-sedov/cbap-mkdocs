!!! note "Аутентификация для доступа к {{ productName }} по HTTP"

    - Для базовой аутентификации при отправке HTTP-запросов в **{{ productName }}** следует использовать учётные данные аккаунта, который имеет разрешение на **вызовы API**. По умолчанию такое разрешение имеют аккаунты с **системной ролью** «**Системные администраторы**».

        При базовой аутентификации для безопасной обработки входящих HTTP-запросов рекомендуется:
    
        - создать специальный аккаунт для авторизации HTTP-запросов;
        - создать системную роль с разрешением на **вызовы API**;
        - добавить в данную системную роль аккаунт для HTTP-запросов.

        См. _[Аккаунты][accounts]_ и _[Системные роли][system_roles]_.

    - Кроме того, можно использовать аутентификацию посредством ключей API. См. _[Ключи аутентификации API][authentication_keys]_.