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

## **Задание 2: Настройка HTTPS с Secrets**  
### **Задача**  
Развернуть приложение с доступом по HTTPS, используя самоподписанный сертификат.

### **Шаги выполнения**  
1. **Сгенерировать SSL-сертификат**
```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout tls.key -out tls.crt -subj "/CN=myapp.example.com"
```
2. **Создать Secret**
3. **Настроить Ingress**
4. **Проверить HTTPS-доступ**

### **Что сдать на проверку**  
- Манифесты:
  - `secret-tls.yaml`
  - `ingress-tls.yaml`
- Скриншот вывода `curl -k`

---

### Решение

### Манифесты

[service-web.yaml](task2/service-web.yaml) — Service типа ClusterIP.

[ingress-tls.yaml](task2/ingress-tls.yaml) — Ingress с настройкой HTTPS.

[secret-tls.example.yaml](task2/secret-tls.example.yaml) — шаблон TLS Secret.

Проверка HTTPS-доступа: успешный ответ HTTP/2 200 и HTML-содержимое страницы


![3](images/3.png)
