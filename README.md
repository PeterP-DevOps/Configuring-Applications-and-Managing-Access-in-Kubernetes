# Домашнее задание к занятию «Настройка приложений и управление доступом в Kubernetes» - Петр Петров
## **Задание 1: Работа с ConfigMaps**
### **Задача**
Развернуть приложение (nginx + multitool), решить проблему конфигурации через ConfigMap и подключить веб-страницу.

### **Шаги выполнения**
1. **Создать Deployment** с двумя контейнерами
   - `nginx`
   - `multitool`
3. **Подключить веб-страницу** через ConfigMap
4. **Проверить доступность**

### **Что сдать на проверку**
- Манифесты:
  - `deployment.yaml`
  - `configmap-web.yaml`
- Скриншот вывода `curl` или браузера

---

### Решение

### Манифесты

[deployment.yaml](task1/deployment.yaml)

[configmap-web.yaml](task1/configmap-web.yaml)

Оба контейнера успешно запущены.

![Pods Running](images/1.png)

Проверка веб-страницы

`curl http://127.0.0.1:8080`

![Curl Result](images/2.png)

