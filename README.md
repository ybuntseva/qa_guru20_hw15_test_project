# Проект по автоматизации тестирования для компании Lamoda
<p  align="center">
<a href="https://www.lamoda.ru/"><img src="./images/icons/Lamoda_logo.svg" width="100"></a>
</p>

> Lamoda - один из крупнейших интернет-магазинов в России и СНГ. С 2014 по 2022 год входил в состав Global Fashion Group.

### :pushpin: Содержание:

+ [Описание](#Описание)
+ [Технологии и инструменты](#computer-технологии-и-инструменты)
+ [Варианты запуска](#Варианты-запуска)
    + [Запуск тестов из терминала](#Команды-для-gradle)
    + [Запуск в Jenkins](#-запуск-в-jenkins)
+ [Уведомления в Telegram](#-telegram-уведомления)
+ [Результаты тестов в Allure Report](#-результаты-тестов-в-allure-report)
+ [Интеграция с Allure TestOps](#-интеграция-с-allure-testOps)
+ [Интеграция с Jira](#-интеграция-с-jira)
+ [Видео примера запуска тестов в Selenoid](#-видео-запуска-тестов-в-selenoid)

### :computer: Технологии и инструменты

[<img src="./images/icons/IDEA-logo.svg" alt="java_17" width="45" height="45"/>](https://www.oracle.com/ru/java/technologies/javase-jre8-downloads.html)
[<img src="./images/icons/java-logo.svg" alt="intellij_idea" width="45" height="45"/>](https://www.oracle.com/ru/java/technologies/javase-jre8-downloads.html)
[<img src="./images/icons/gradle-logo.svg" alt="gradle" width="45" height="45"/>](https://gradle.org/)
[<img src="./images/icons/junit5-logo.svg" alt="junit_5" width="45" height="45"/>](https://junit.org/junit5/)
[<img src="./images/icons/selenide-logo.svg" alt="selenide" width="45" height="45"/>](https://ru.selenide.org/)
[<img src="./images/icons/allure-ee-logo.svg" alt="allure_test_ops" width="45" height="45"/>](https://qameta.io/)
[<img src="./images/icons/allure-Report-logo.svg" alt="allure" width="45" height="45"/>](https://qameta.io/allure-report/)
[<img src="./images/icons/jenkins-logo.svg" alt="jenkins" width="45" height="45"/>](https://www.jenkins.io/)
[<img src="./images/icons/selenoid-logo.svg" alt="selenoid" width="45" height="45"/>](https://aerokube.com/selenoid/latest/)
[<img src="./images/icons/github-mark.svg" alt="github" width="45" height="45"/>](https://github.com/)
[<img src="./images/icons/jira-logo.svg" alt="jira" width="45" height="45"/>](https://www.atlassian.com/software/jira)
[<img src="./images/icons/Telegram.svg" alt="telegram" width="45" height="45"/>](https://en.wikipedia.org/wiki/Telegram_(software))

Автотесты в этом проекте написаны на `Java` с использованием `Selenide` фреймворка.\
`Gradle` - используется как инструмент автоматизации сборки.  \
`JUnit5` - для выполнения тестов.\
`Jenkins` - CI/CD для запуска тестов удаленно.\
`Selenoid` - для удаленного запуска браузера в `Docker` контейнерах.\
`Allure Report` - для визуализации результатов тестирования.\
`Telegram Bot` - для уведомлений о результатах тестирования.

[Вернуться к оглавлению ⬆](#pushpin-содержание)

## <a name="GradleCommand">Команды для Gradle</a>

***Локальный запуск:***
```bash  
gradle clean test
```

***Удалённый запуск через Jenkins:***
```bash  
clean test
"-Dbrowser=${browser}"
"-DbrowserVersion=${browserVersion}"
"-DbrowserSize=${browserSize}"
"-DbaseUrl=${baseUrl}"
"-DremoteUrl=${remoteUrl}"
```

Дополнительные параметры:
> `-DremoteUrl=` - логин, пароль и адрес удаленного сервера Selenoid\
> `-DbaseUrl=` - адрес тестируемого сайта\
> `-Dbrowser=chrome` - выбор браузера (по умолчанию - chrome)\
> `-DbrowserVersion=100.0` - установка версии браузера\
> `-DbrowserSize=1920x1080` - установка разрешения окна браузера.

[Вернуться к оглавлению ⬆](#pushpin-содержание)

## <img src="./images/icons/jenkins-logo.svg" title="Jenkins" width="4%"/> <a name="Запуск в Jenkins">Запуск в [Jenkins](https://jenkins.autotests.cloud/job/qa_guru20_hw15_test_project2/)</a>
Главная страница сборки:
<p  align="center">
<img src="images/screenshots/jenkins.png" width="950">
</p>

Параметризованное задание Jenkins может быть запущено с необходимыми ***Browser***, ***Browser Version***, ***Browser Size*** и ***Task***:
<p  align="center">
<img src="images/screenshots/jenkins-parameters.png" alt="JenkinsBuildParameters" width="950">
</p>

После завершения сборки результаты тестирования доступны в:
>- <code><strong>*Allure Report*</strong></code>
>- <code><strong>*Allure TestOps*</strong></code> - результаты загружаются туда и тест-кейсы могут автоматически обновляться в соответствии с последними изменениями в коде.

[Вернуться к оглавлению ⬆](#pushpin-содержание)

# <img width="4%" style="vertical-align:middle" title="Telegram" src="images/icons/Telegram.svg"> <a>Telegram уведомления</a>
После завершения сборки, бот созданный в <code>Telegram</code>, автоматически обрабатывает и отправляет сообщение с результатом.
<p  align="center">
<img src="images/screenshots/telegram-notification.png" width="550">
</p>

[Вернуться к оглавлению ⬆](#pushpin-содержание)

# <img width="4%" style="vertical-align:middle" title="AllureReport" src="images/icons/allure-Report-logo.svg"> <a name="AllureReport">Результаты тестов в [Allure Report](https://jenkins.autotests.cloud/job/qa_guru20_hw15_test_project2/5/allure/#)</a>

## Главная страница
Главная страница отчета Allure содержит следующие блоки:

>- <code><strong>*ALLURE REPORT*</strong></code> - отображает дату и время теста, общее количество запущенных тестов, а также диаграмму с процентом и количеством успешных, упавших и сломавшихся в процессе выполнения тестов
>- <code><strong>*TREND*</strong></code> - отображает тенденцию выполнения тестов для всех запусков
>- <code><strong>*SUITES*</strong></code> - отображает распределение тестов по сьютам
>- <code><strong>*CATEGORIES*</strong></code> - отображает распределение неудачных тестов по типам дефектов
<p align="center">
  <img src="images/screenshots/allure-report.png" width="950">
</p>

## Список тестов с шагами и тестовыми артефактами
На странице список тестов, сгруппированных по наборам, с указанием статуса для каждого теста.\
Может быть показана полная информация о каждом тесте: теги, продолжительность, подробные шаги.

Также доступны дополнительные тестовые артефакты:
>- Screenshot
>- Page Source
>- Browser console log
>- Video

<p align="left">
  <img src="images/screenshots/allure-suites.png" alt="AllureResult" width="950">
</p>

[Вернуться к оглавлению ⬆](#pushpin-содержание)

# <img width="4%" style="vertical-align:middle" title="Allure TestOps" src="images/icons/allure-ee-logo.svg"> <a>Интеграция с [Allure TestOps](https://allure.autotests.cloud/project/3631/dashboards)</a>
> Ссылка доступна только авторизованным пользователям.

Выполнена интеграция сборки <code>Jenkins</code> с <code>Allure TestOps</code>.
Результат выполнения автотестов отображается в <code>Allure TestOps</code>
На Dashboard в <code>Allure TestOps</code> отображена статистика пройденных тестов.

Тест-кейсы в проекте импортируются и постоянно обновляются из кода,
поэтому нет необходимости в синхронизации ручных тест-кейсов и автотестов.\
Достаточно создать и обновить автотест в коде и тест-кейс всегда будет в актуальном состоянии.

## Allure TestOps Dashboard

<p align="center">
  <img src="images/screenshots/allure-testops-dashboard.png" alt="AllureTestOps" width="950">
</p>

## Allure TestOps Test Cases

<p align="center">
  <img src="images/screenshots/allure-testops-testcases.png" alt="AllureTestOpsTests" width="950">
</p>

[Вернуться к оглавлению ⬆](#pushpin-содержание)

# <img width="4%" style="vertical-align:middle" title="Jira" src="images/icons/jira-logo.svg"> <a>Интеграция с Jira</a>
Реализована интеграция <code>Allure TestOps</code> с <code>Jira</code>, в тикете отображается информация, какие тест-кейсы были написаны в рамках задачи и результат их прогона.
<p align="center">
  <img src="images/screenshots/jira.png" alt="JiraIntegration" width="950">
</p>

[Вернуться к оглавлению ⬆](#pushpin-содержание)

# <img width="4%" style="vertical-align:middle" title="Selenoid" src="images/icons/selenoid-logo.svg"> <a>Видео запуска тестов в Selenoid</a>
К каждому тесту в отчете прилагается видео прохождения теста:
<p align="center">
  <img src="images/screenshots/video.gif" alt="JiraIntegration">
</p>

[Вернуться к оглавлению ⬆](#pushpin-содержание)


