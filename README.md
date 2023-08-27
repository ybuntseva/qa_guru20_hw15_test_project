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

<p  align="center">
  <code><img width="5%" title="IntelliJ IDEA" src="./images/icons/IDEA-logo.svg"></code>
  <code><img width="5%" title="Java" src="./images/icons/java-logo.svg"></code>
  <code><img width="5%" title="Selenide" src="./images/icons/selenide-logo.svg"></code>
  <code><img width="5%" title="Selenoid" src="./images/icons/selenoid-logo.svg"></code>
  <code><img width="5%" title="Gradle" src="./images/icons/gradle-logo.svg"></code>
  <code><img width="5%" title="JUnit5" src="./images/icons/junit5-logo.svg"></code>
  <code><img width="5%" title="Allure Report" src="./images/icons/allure-Report-logo.svg"></code>
  <code><img width="5%" title="Allure TestOps" src="./images/icons/allure-ee-logo.svg"></code>
  <code><img width="5%" title="Github" src="./images/icons/github-mark.svg"></code>
  <code><img width="5%" title="Jenkins" src="./images/icons/jenkins-logo.svg"></code>
  <code><img width="5%" title="Jira" src="./images/icons/jira-logo.svg"></code>
  <code><img width="5%" title="Telegram" src="./images/icons/Telegram.svg"></code>

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

