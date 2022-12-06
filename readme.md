# PHP клиент для CapMonsterCloud api

#### Использование
```php
    include './client/Client.php';
    include './client/src/captcha/ImageToText.php';
    
    $client = new Client("your_client_key");
    
    $captchaBody = "body"
    //создание объекта запроса к api
    $captchaRequest = new ImageToTextRequest($captchaBody);
    
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