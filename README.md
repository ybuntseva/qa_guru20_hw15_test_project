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
+ [Видео примера запуска тестов в Selenoid](#-видео-запуска-тестов-в-selenoid)

<a id="tools"></a>
## <a name="Технологии и инструменты">**Технологии и инструменты:**</a>

[<img src="./images/icons/IDEA-logo.svg" alt="java_17" width="45" height="45"/>](https://www.oracle.com/ru/java/technologies/javase-jre8-downloads.html)
[<img src="./images/icons/java-logo.svg" alt="intellij_idea" width="45" height="45"/>](https://www.oracle.com/ru/java/technologies/javase-jre8-downloads.html)
[<img src="./images/icons/gradle-logo.svg" alt="gradle" width="45" height="45"/>](https://gradle.org/)
[<img src="./images/icons/junit5-logo.svg" alt="junit_5" width="45" height="45"/>](https://junit.org/junit5/)
[<img src="./images/icons/selenide-logo.svg" alt="selenide" width="45" height="45"/>](https://ru.selenide.org/)
[<img src="./images/icons/allure-ee-logo.svg" alt="test_ops" width="45" height="45"/>](https://qameta.io/)
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

