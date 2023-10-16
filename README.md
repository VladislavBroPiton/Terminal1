**Git** — система управления версиями с распределенной архитектурой, в Git каждая рабочая копия кода сама по себе является репозиторием. Это позволяет всем разработчикам хранить историю изменений в полном объеме.     
#### Рассмотрим пример:   
разработчик Элис меняет исходный код. Она добавляет функцию для будущей версии 2.0, после чего делает коммит и сопровождает изменения описанием. Затем она разрабатывает другую функцию и делает еще один коммит. Разумеется, эти изменения сохраняются в истории в виде отдельных рабочих элементов. Затем Элис переключается на ветку, соответствующую версии 1.3 того же ПО — так она сможет исправить баг, затрагивающий эту конкретную версию. Это нужно, чтобы команда Элис могла выпустить версию 1.3.1 с исправлениями до завершения работы над версией 2.0. Затем Элис вернется к ветке для версии 2.0 и продолжит работу над соответствующими функциями. Все перечисленные действия можно выполнить без доступа к сети, поэтому система Git отличается быстротой и надежностью, даже если работать в самолете. Когда Элис будет готова отправить все внесенные изменения в удаленный репозиторий, ей останется лишь выполнить команду push.     
Одно из самых больших преимуществ Git — возможность ветвления. Функциональные ветки служат изолированной средой для каждого изменения в базе кода. Когда разработчик хочет приступить к работе над частью проекта — неважно, большой или маленькой, — он создает новую ветку. Благодаря этому в главной ветке всегда сохраняется высокое качество кода, приемлемое для развертывания в рабочей среде.    
Использование функциональных веток не только более надежно, чем прямое редактирование окончательного кода, но и дает организационные преимущества: процесс разработки можно представить с такой же степенью детализации, которую имеет ваш agile-бэклог. Например, можно реализовать политику, в которой каждая заявка в Jira будет выполняться в отдельной функциональной ветке.

#### Мои часто используемые команды:  
1. **git fetch** — это основная команда, которая используется для загрузки содержимого из удаленного репозитория. Чтобы обновить локальный репозиторий до состояния удаленного репозитория, команда git fetch используется в сочетании с командами **git remote** , **git branch** , **git checkout** и **git reset**.  
2. **git pull** используется для извлечения и загрузки содержимого из удаленного репозитория и немедленного обновления локального репозитория этим содержимым. Слияние удаленных вышестоящих изменений в локальный репозиторий — это обычная задача рабочего процесса, возникающая при совместной работе на основе системы Git.  
3. **git push** используется для выгрузки содержимого локального репозитория в удаленный репозиторий. Она позволяет передать коммиты из локального репозитория в удаленный.  
4.  **git add** состоит в переносе ожидающих изменений из рабочего каталога в раздел проиндексированных файлов Git. **git add** добавляет содержимое рабочего каталога в индекс (staging area) для последующего коммита.  
5. **git commit** сохраняет снимок состояния из раздела проиндексированных файлов в истории коммитов репозитория. **commit** значит «фиксировать»  (**git commit -m "update"**)
   
   