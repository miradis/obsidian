#Знания
### Создание Router
Создаем для проекта папка router, внутри создаем две папки
- index.js - файл где создается роутер
- routes - список маршрутов

<hr> 

#### index.js
Создаем instance с помощью createRouter, который принимает в себя объект двумя параметрами: routes, history
```
import {routes} from './routesc'
import { createRouter, createWebHistory } from 'vue-router'

const router = createRouter({
history: createWebHistory(process.env.BASE_URL), // Используем createWebHistory
routes, // Передаем массив маршрутов
})

export default router;
```

<hr>
#### routes.js
Объявляем массив объектов, где каждый объект содержит следующие поля: 

*name* - название каждого 
*path* - путь в URL для перемещения по routes
*component* компонент который нужно отрисовать, если придет по указанному пути
*meta* - доп информация о маршруте,  в виде объекта  
```
export const routes = [

{
path: "/",
name: "nullPage",
component: () => import('src/pages/landing/NullPage.vue')
},

{
path: "/aboutUs",
name: "aboutUs",
component: () => import('src/pages/aboutUs/AboutUsPage.vue')
}
]
```

<hr>

#### main.js
Нужно подключить  router в экземпляр app (vue):

```
const app = createApp();

app.use(routes) //подключение маршрутизатора к приложению
.provide("$router, router) // глобальный вызов по $router
```

## Особенности Vue Router
Можно передавать в router props и ловить в компоненте в отделе props 
Вот что говорит Чат Гпт на этот счет: