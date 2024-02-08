**Git** — система управления версиями с распределенной архитектурой, в Git каждая рабочая копия кода сама по себе является репозиторием. Это позволяет всем разработчикам хранить историю изменений в полном объеме.       
#### Рассмотрим пример:   
  * разработчик Элис меняет исходный код. Она добавляет функцию для будущей версии 2.0, после чего делает коммит и сопровождает изменения описанием. Затем она разрабатывает другую функцию и делает еще один коммит. Разумеется, эти изменения сохраняются в истории в виде отдельных рабочих элементов. Затем Элис переключается на ветку, соответствующую версии 1.3 того же ПО — так она сможет исправить баг, затрагивающий эту конкретную версию. Это нужно, чтобы команда Элис могла выпустить версию 1.3.1 с исправлениями до завершения работы над версией 2.0. Затем Элис вернется к ветке для версии 2.0 и продолжит работу над соответствующими функциями. Все перечисленные действия можно выполнить без доступа к сети, поэтому система Git отличается быстротой и надежностью, даже если работать в самолете. Когда Элис будет готова отправить все внесенные изменения в удаленный репозиторий, ей останется лишь выполнить команду push.   
    
Одно из самых больших преимуществ Git — возможность ветвления. Функциональные ветки служат изолированной средой для каждого изменения в базе кода. Когда разработчик хочет приступить к работе над частью проекта — неважно, большой или маленькой, — он создает новую ветку. Благодаря этому в главной ветке всегда сохраняется высокое качество кода, приемлемое для развертывания в рабочей среде.      
Использование функциональных веток не только более надежно, чем прямое редактирование окончательного кода, но и дает организационные преимущества: процесс разработки можно представить с такой же степенью детализации, которую имеет ваш agile-бэклог. Например, можно реализовать политику, в которой каждая заявка в Jira будет выполняться в отдельной функциональной ветке.

#### Мои часто используемые команды:      
1. **git fetch** — это основная команда, которая используется для загрузки содержимого из удаленного репозитория. Чтобы обновить локальный репозиторий до состояния удаленного репозитория, команда git fetch используется в сочетании с командами **git remote** , **git branch** , **git checkout** и **git reset**.  
2. **git pull** используется для извлечения и загрузки содержимого из удаленного репозитория и немедленного обновления локального репозитория этим содержимым. Слияние удаленных вышестоящих изменений в локальный репозиторий — это обычная задача рабочего процесса, возникающая при совместной работе на основе системы Git.  
3. **git push** используется для выгрузки содержимого локального репозитория в удаленный репозиторий. Она позволяет передать коммиты из локального репозитория в удаленный.  
4.  **git add** состоит в переносе ожидающих изменений из рабочего каталога в раздел проиндексированных файлов Git. **git add** добавляет содержимое рабочего каталога в индекс (staging area) для последующего коммита.  
5. **git commit** сохраняет снимок состояния из раздела проиндексированных файлов в истории коммитов репозитория. **commit** значит «фиксировать»  (**git commit -m "update"**)
   
   
git branch создание ветки
git   checkout переход в ветку

### Чтобы игнорировать определенные директории и файлы и предотвратить их попадание в коммиты в Git, следуйте этой последовательности действий:
**1. Создайте файл .gitignore в корневой директории вашего проекта (если его еще нет).**   
**2. Откройте файл .gitignore в текстовом редакторе и добавьте в него паттерны, описывающие директории и файлы, которые нужно игнорировать.**   
Например, если вам нужно игнорировать директорию node_modules и файлы с расширением .log, вы можете добавить следующие строки в .gitignore:   
```
node_modules/   
*.log   
```
Обратите внимание, что / в конце строки указывает на директорию, а * перед расширением указывает на все файлы с этим расширением в любой директории.   
**3. Сохраните и закройте файл .gitignore.**   
**4. Убедитесь, что Git учитывает файл .gitignore с помощью команды `git status` или `git ls-files --others --ignored`.**      
Обнаруженные файлы и директории, указанные в .gitignore, должны отображаться в списке игнорируемых файлов.   
**5. Выполните команду git add .gitignore для добавления .gitignore в индекс.**   
**6. Закоммитьте изменения с помощью команды git commit -m "Добавлен .gitignore для игнорирования файлов и директорий".**   
Теперь указанные в .gitignore файлы и директории будут игнорироваться при следующих коммитах.   
При выполнении команды git status вы увидите, что игнорируемые файлы и директории не отображаются в списках изменений или неотслеживаемых файлов.   

### Закоммитить часть кода   
**Чтобы закоммитить только часть кода, отвечающую за взаимодействие с серверной частью приложения, вы можете использовать интерактивное добавление изменений в Git. Вот команда, которую можно использовать:**   
```
git add -p   
```
После выполнения этой команды Git отобразит вам список изменений, среди которых вы можете выбрать конкретные части кода для коммита. Вы увидите символы, представляющие различные действия, такие как y (Yes), n (No), s (Split), q (Quit), и т. д.   

Чтобы выбрать конкретные изменения для коммита, вы можете использовать следующие действия:   
- y (Yes): Добавить изменение в коммит.      
- n (No): Пропустить изменение и не добавлять его в коммит.   
- s (Split): Разбить изменение на более мелкие части для выборочного добавления.   
- q (Quit): Завершить интерактивное добавление изменений.   
Выберите y для изменений, относящихся к взаимодействию с серверной частью приложения, и n для остальных изменений. После выбора изменений Git предложит вам ввести сообщение коммита.   
После выбора всех нужных изменений и ввода сообщения коммита выполните команду:   
```
git commit   
```
### Откат последнего коммита без сохранения изменений в рабочей директории   
Чтобы откатить последний коммит и при этом не сохранять изменения в рабочей директории, вы можете использовать команду `git reset` с флагом --hard. Вот как это сделать:   
1. Откройте терминал или командную строку и перейдите в директорию вашего Git-репозитория   
2. Введите следующую команду:   
```
git reset --hard HEAD~1   
```
Эта команда отменит последний коммит и переместит указатель HEAD на предыдущий коммит, удаляя все изменения из последнего коммита.   
Если вы хотите откатить более чем один коммит, замените 1 в команде на соответствующее число коммитов, которые вы хотите откатить.  
 
3. После выполнения команды Git сообщит вам об успешном откате коммита. Все изменения, внесенные в последнем коммите, будут удалены, и рабочая директория будет синхронизирована с откатом.   

Обратите внимание, что данная команда изменяет историю коммитов вашего репозитория. Если вы уже опубликовали коммиты в удаленный репозиторий, вам может потребоваться выполнить команду `git push --force` для синхронизации удаленного репозитория с вашим локальным состоянием. Однако будьте осторожны с использованием `git push --force`, так как это может повредить работу других разработчиков, работающих с этим репозиторием.   
