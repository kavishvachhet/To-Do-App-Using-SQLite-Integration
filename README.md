# 📝 Flutter To-Do App

A clean and minimal **To-Do List app** built using **Flutter**, designed to help you stay organized and productive. Add, delete, and mark tasks as completed – all in a beautiful cross-platform UI.

## 🚀 Features

- ✅ Add new tasks
- 🗑️ Delete tasks
- ✏️ Edit task titles
- 📌 Mark tasks as completed/incomplete
- 🌙 Light/Dark mode support
- 💾 Persistent local storage using `sqflite` or `shared_preferences`
- 📱 Responsive UI (Android, iOS)

## 📸 Screenshots

| Home Screen | Dark Mode |
|------------|------------|
| ![Home](screenshots/home.png) | ![Dark](screenshots/dark.png) |

## 🛠️ Tech Stack

- **Flutter** - UI SDK
- **Dart** - Programming language
- **State Management** - Provider  / setState
- **Local Storage** - `sqflite`  / `shared_preferences`

## 📦 Packages Used

```yaml
dependencies:
  flutter:
    sdk: flutter
  provider: ^6.0.0
  shared_preferences: ^2.0.15
  sqflite: ^2.0.0+4
  path_provider: ^2.0.11
