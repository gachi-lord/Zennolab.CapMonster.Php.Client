# PHP клиент для CapMonsterCloud api

#### Использование
```php
    include './client/Client.php';
    include './client/src/captcha/ImageToText.php';
    
    $clientOptions = [
        "clientKey" => "your_client_key"
    ];
    $client = new Client($clientOptions);
    
    $captchaOptions = [
        "body" => "baset64_body"
    ];
    //создание объекта запроса к api
    $captchaRequest = new ImageToTextRequest($captchaOptions);
    
    //решение капчи
    $solution = $client->solve($captchaRequest);
    var_dump($solution);
```

#### Формат ответа
 Результат метода solve всегда содержит два поля: bool result, индикатор успеха запроса, и поле mixed message, содержащее текстовое описание ошибки или объект успешного ответа от сервера.

#### Поддерживаемые виды капч

- FunCaptchaTask
- FunCaptchaTaskProxyless
- GeeTestTask
- GeeTestTaskProxyless
- HCaptchaTask
- HCaptchaTaskProxyless
- ImageToTextTask
- RecaptchaV2Task
- RecaptchaV2TaskProxyless
- RecaptchaV3TaskProxyless
- RecaptchaV2EnterpriseTask
- RecaptchaV2EnterpriseTaskProxyless