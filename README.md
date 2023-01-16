## Запуск проекта
Чтобы его запустить надо склонировать репу.
    git clone https://github.com/Sararun/test-task-front.git
Может понадобиться установка nodejs и npm.
Введите в консоль:
    cd ~
    curl -sL https://deb.nodesource.com/setup_18.x -o nodesource_setup.sh
    sudo bash nodesource_setup.sh
    sudo apt install nodejs
    sudo apt install npm
Нужно будет установить библиотеку axios
npm install axios
И библиотеку element-plus
npm install element-plus --save
    
В консоли написать npm run dev.
## Работа в программе
Чтобы форма отправилась надо вписать данные соответсвующие правилам валидации:
Поле name должно быть: не пустым, строчным, не меьше 3 и не больше 15 символов.
Поле phone должно быть: не пустым, строчным, не меньше 10 и не больше 11 символов.
Поле email должно быть: не пустым, должно быть почтой( то есть с значком @, название почтовой организации (mail, gmail и т.д.), и должен быть домен верхнего уровня (ru, com, net).

## Обяснение кода
В этом проекте я реализовал форму, 
которая с помощью библиотеки axios отправляет данные post запросом на бэк в проект, 
test-task-kontur, на бэке пройдёт валидация если что-то будет не так, 
то будет возвращаться ответ и фронт будет выводить его на экран с помощью библиотеки element-plus.
Если форма отправилась выйдет сообщение, что всё хорошо и данные из формы сотрутся.
## Единтсенное окно
![1](https://user-images.githubusercontent.com/91774585/212557952-4892057b-5d8f-4ebc-9a32-a03092d10d5e.png)
