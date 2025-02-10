1) Прописываем 'window.addEventListener('DOMContentLoaded', () =>{}', чтобы JS начинал работать после того, как загрузиться DOM элементы
2) Функция hideTabContent:

let hideTabContent = a => {
    for (let i = a; i < tabContent.length; i++) {
        tabContent[i].classList.remove('show');
        tabContent[i].classList.add('hide');
    }
};
Эта функция скрывает все элементы tabContent, начиная с индекса a.

Удаляет класс show и добавляет класс hide для каждого элемента tabContent.

3) Инициализация скрытия вкладок:

hideTabContent(1);
Скрывает все вкладки, начиная со второй (индекс 1). Первая вкладка остается видимой.

Функция showTabContent:

let showTabContent = b => {
    if (tabContent[b].classList.contains('hide')) {
        tabContent[b].classList.remove('hide');
        tabContent[b].classList.add('show');
    }
};
Эта функция отображает элемент tabContent с индексом b.

Если элемент содержит класс hide, он удаляется и добавляется класс show.

4) Обработчик события click:

info.addEventListener('click', event => {
    let target = event.target;
    if (target && target.classList.contains('info-header-tab')) {
        for (let i = 0; i < tab.length; i++) {
            if (target == tab[i]) {
                hideTabContent(0);
                showTabContent(i);
                break;
            }
        }
    }
});
Добавляет обработчик события click на элемент info.

Когда пользователь нажимает на элемент внутри info, проверяется, является ли этот элемент вкладкой (имеет класс .info-header-tab).

Если это вкладка, то:

Скрываются все вкладки с помощью hideTabContent(0).

Отображается содержимое, соответствующее выбранной вкладке, с помощью showTabContent(i).
