# MultiHub Platform | Micro-Frontend Demo

[![React](https://img.shields.io/badge/React-19.1.1-blue)](https://reactjs.org/)
[![Vue](https://img.shields.io/badge/Vue-3.3.0-green)](https://vuejs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)](https://www.typescriptlang.org/)
[![Module Federation](https://img.shields.io/badge/Module%20Federation-✓-orange)](https://module-federation.io/)


**Демонстрационный проект**, демонстрация современной микрофронтенд-архитектуры с использованием React, Vue и возможностей работы в реальном времени. Это экспериментальная реализация, а не готовое к использованию приложение..

> 🎯 **Важное замечание**: В реальном продакшн-приложении я бы не стала использовать столько различных технологий одновременно. Этот проект демонстрирует навыки интеграции и архитектурного мышления, а не рекомендации по стеку технологий для production.

## 🏗️ Архитектура

### Микро-фронтенд подход
Приложение разделено на независимые модули, которые разрабатываются и деплоятся отдельно:

```
TeamHub Platform
├── 🏠 Host App (React) # Shell-приложение, оркестратор
├── 📊 Project Management (Vue) # Управление проектами и задачами
├── 👥 Team & Analytics (React) # Команда и аналитика
└── 🔌 Shared Communication Layer # Общий слой коммуникации
```

### Технологический стек по модулям

| Модуль | Технологии | Назначение |
|--------|------------|------------|
| **Host (Shell)** | React 19, Redux Toolkit, RTK Query, React Router, Tailwind CSS, WebSocket | Оркестрация, глобальное состояние, авторизация |
| **Project Management** | Vue 3, Pinia, Vue Router, Vuetify, Vuelidate | CRUD проектов, Kanban доски, управление задачами |
| **Team & Analytics** | Vue 3, Chart.js, Pinia, Vue Router | Визуализация данных, управление командой |

## 🚀 Ключевые демонстрационные аспекты

### 1. Межфреймворковая коммуникация
- **Custom Events** для loose coupling между React и Vue
- **Redux Toolkit** как глобальное хранилище состояния
- **WebSocket** для real-time обновлений

### 2. Независимость модулей
- Каждый микро-фронтенд имеет собственную codebase
- Изолированные стейт-менеджеры (Pinia внутри Vue, RTK в хосте)
- Independent routing и бизнес-логика

### 3. Производительность и оптимизация
- Code splitting через Module Federation
- Shared dependencies (react, vue) в single instance
- Lazy loading микро-фронтендов

## 📁 Структура проекта
```
multiHub/
│── host-app/ # React shell application
│── project-management/ # Vue micro-frontend
│── team-analytics/ # React micro-frontend
└── README.md
```


## 🛠️ Установка и запуск

```bash
# Клонирование репозитория
git clone https://github.com/DalilaM25/multyHub.git
cd multyHub

# Запуск
npm run initstart


# Или запуск отдельных приложений
npm run install:host
npm run dev:host        # Хост-приложение React (порт 5000)

npm run install:remote
npm run dev:remote    # Vue microfront (порт 5001)  

