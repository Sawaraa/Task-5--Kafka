# 📧 Email Service (Kafka + Elasticsearch)

Сервіс для обробки та відправки електронних листів, який отримує повідомлення з Kafka, зберігає історію в Elasticsearch та надсилає листи через SMTP (Mailtrap).

---

## 🛠 Технологічний стек
* **Java / Spring Boot 3**
* **Apache Kafka** (Consumer)
* **Elasticsearch & Kibana** (Зберігання та візуалізація)
* **Docker & Docker Compose**
* **Mailtrap** (SMTP сервер для тестування)

---

## 🚀 Як запустити проект
Y корені проекту файл `.env` додайте ваші налаштування Mailtrap (або іншого SMTP-провайдера):
```env
MAIL_HOST=sandbox.smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=ваш_username
MAIL_PASSWORD=ваш_password
```

### 2. Запуск через Docker Compose
Щоб підняти всю інфраструктуру та сам сервіс однією командою, виконайте
```bash
docker-compose up --build
```
### 3. Запуск для розробки
Якщо запускати код в IDE то:
щоб звільнити порт 8081
```bash
docker stop email-service
```
щоб звільнити порт 8081, і запустити локально 

## 📊 Доступ до сервісів

Після успішного запуску всі компоненти системи доступні за наступними адресами:

| Сервіс | Адреса | Опис |
| :--- | :--- | :--- |
| **Email Service** | `http://localhost:8081` | Ваш Spring Boot додаток (REST API та Kafka Consumer) |
| **Elasticsearch** | `http://localhost:9200` | База даних для зберігання історії надісланих листів |
| **Kibana** | `http://localhost:5601` | Візуальний інтерфейс для керування та аналізу даних Elastic |
| **Zookeeper** | `http://localhost:2181` | Координатор для стабільної роботи кластера Kafka |
