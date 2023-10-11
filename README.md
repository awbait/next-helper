# next-helper

## Features
- [x] Показать/скрыть интерфейс
- [x] Готовка (один раз)
- [x] АвтоГотовка
- [x] Закупка продукции в доме
- [x] Закрыть игру
- [x] Базовая ловля
- [x] Закрыть бота
- [ ] Открыть репорт (Доп возможность авто-заполнения при срочности?)
- [ ] Сделать релог
- [ ] Сбор территории
- [ ] Сбор 4х бутылок
- [ ] Сбор картошки (Право/Лево/Центр)
- [ ] Приготовление в цехах (Картоха/алкашка)
- [ ] АнтиАФК с открытием/закрытием телефона? (оружие в руках)
- [ ] Ловля бумаг по минималке и допустим + N процентов сверху
- [ ] Удерживать кнопку войса для музыки включенной, даже если игра свернута
- [ ] Таймер на готовку? Типо через сколько можно приготовить еще раз
- [ ] Уведомление в ТГ/ДС если выкинуло с игры
- [ ] Уведомление, что кинули территорию (скан правой части экрана)
- [ ] Быстрый выкуп бизов с госса

## Build launcher
```
"C:/Program Files/AutoHotkey/Compiler/Ahk2Exe.exe" /in "./launcher/launcher.ahk" /out "../build/launcher.exe" /icon "C:/work/next-helper/images/logo.ico"
"C:/Program Files/AutoHotkey/Compiler/Ahk2Exe.exe" /in "helper.ahk" /out "./build/helper.exe"
```

## Сгенерировать самоподписанный сертификат
```
$cert = New-SelfSignedCertificate -Subject "HelperNextrp" -CertStoreLocation "cert:\LocalMachine\My" -type CodeSigning
$pwd = ConvertTo-SecureString -String "123456" -Force -AsPlainText
Export-PfxCertificate -cert $cert -FilePath HelperNextrp.pfx -Password $pwd
```

## Подписать выполняемый файл
Запустить Developer Command Prompt и выполнить:
```
signtool.exe sign /f HelperNextrp.pfx /fd sha1 /p 123456 ./build/launcher.exe
```
