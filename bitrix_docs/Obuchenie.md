[Обучение](/api_help/learning/index.php)

Для разработчиков

Для разработчиков
=================

Перед использованием модуля **Обучение** необходимо проверить, установлен ли он, и подключить его при помощи конструкции:

```
<?
if (CModule::IncludeModule("learning"))
{
	//здесь можно использовать функции модуля
}
?>Копировать
```

  
Модуль включает в себя следующие Компоненты 2.0:
  

| **Компоненты модуля** | | |
| --- | --- | --- |
| **Название** | **Имя в пространстве имен bitrix** | **Описание** |
| [Детальный вывод главы](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_chapter_detail.php) | **learning.chapter.detail** | Производит детальный вывод главы курса. |
| [Учебный курс (комплексный компонент)](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_course.php) | **learning.course** | Осуществляет полноценный вывод учебного курса. |
| [Все материалы курса](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_course_contents.php) | **learning.course.contents** | Выводит все материалы курса на одной странице. |
| [Детальный вывод курса](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_course_detail.php) | **learning.course.detail** | С помощью компонента производится детальный вывод курса. |
| [Список курсов](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_course_list.php) | **learning.course.list** | Выводит список курсов. |
| [Дерево курса](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_course_tree.php) | **learning.course.tree** | Выводит иерархию глав и уроков курса. |
| [Детальный вывод урока](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_lesson_detail.php) | **learning.lesson.detail** | Производит детальный вывод урока курса. |
| [Отчет по курсам](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_student_certificates.php) | **learning.student.certificates** | Выводит список пройденных и непройденных курсов текущего пользователя. |
| [Журнал студента](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_student_gradebook.php) | **learning.student.gradebook** | Отображает результаты прохождения тестов. |
| [Профиль студента](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_student_profile.php) | **learning.student.profile** | Отображает результаты прохождения тестов. |
| [Резюме студента](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_student_transcript.php) | **learning.student.transcript** | Отображает информацию о студенте и список полученных им сертификатов. |
| [Контрольный тест](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_test.php) | **learning.test** | Отображает контрольный тест курса. |
| [Список тестов](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_test_list.php) | **learning.test.list** | Выводит список активных тестов курса. |
| [Самопроверка](https://dev.1c-bitrix.ru/user_help/components/services/learning/learning_test_self.php) | **learning.test.self** | Выводит тест для самопроверки. |

Новинки документации в соцсетях: