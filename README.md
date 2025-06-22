# Midas
Project repo for the JPMC Advanced Software Engineering Forage program
Here's your professionally formatted and polished `README.md` file for your **Midas Core** project, ready to copy and paste directly into GitHub:

---

```markdown
# 💰 Midas Core - Transaction Processing System

A Spring Boot microservice built as part of the **JPMorgan Chase & Co. Virtual Software Engineering Internship**. This service processes Kafka-based transaction streams, updates user balances, integrates with an external Incentives API, and exposes a REST API for querying balances.

---

## 🛠️ Technologies Used

- **Java 17** (Eclipse Temurin)
- **Spring Boot** (Web, Data JPA, Test)
- **Apache Kafka**
- **H2 In-Memory Database**
- **Maven**
- **JUnit 5**

---

## 🚀 Features

- ✅ **Kafka Transaction Listener** – Listens to transactions, validates sender/recipient, and updates balances.
- ✅ **Incentives API Integration** – Sends each valid transaction to an external API and adds the returned incentive to the recipient’s balance.
- ✅ **Balance Query Endpoint** – Exposes `/balance?userId={id}` to return a user’s balance (returns `0` if user not found).
- ✅ **In-Memory DB for Testing** – Uses H2 for fast development and test execution.
- ✅ **Automated Testing** – Validated via `TaskFourTests` and `TaskFiveTests`.

---

## 📁 Project Structure

```

src/
├── main/
│   ├── java/com/jpmc/midascore/
│   │   ├── controller/         → REST endpoint for balance
│   │   ├── entity/             → UserRecord, TransactionRecord entities
│   │   ├── repository/         → User and Transaction JPA Repositories
│   │   ├── service/            → Business logic layer
│   │   └── foundation/         → Shared models like Balance.java
│   └── resources/
│       └── application.properties
└── test/
└── java/com/jpmc/midascore/
└── TaskFourTests.java, TaskFiveTests.java

````

---

## 🌐 API Reference

### `GET /balance`

Returns the balance for a given user.

- **URL**: `/balance`
- **Method**: `GET`
- **Query Param**: `userId` (required)
- **Success Response**:
```json
{
  "amount": 250.75
}
````

* **If User Not Found**:

```json
{
  "amount": 0.0
}
```

---

## 🧪 Running the Project Locally

1. **Ensure Incentives API is running**

   ```
   POST http://localhost:8080/incentive
   ```

2. **Start Kafka Broker** (on port `9092`)

3. **Run the application**

   ```bash
   ./mvnw spring-boot:run
   ```

4. **Run tests**

   ```bash
   ./mvnw test
   ```

   Or execute `TaskFourTests` and `TaskFiveTests` from your IDE.

---

## ✅ Test Coverage

| Test Class      | Purpose                                                |
| --------------- | ------------------------------------------------------ |
| `TaskFourTests` | Validates transaction + incentive workflow             |
| `TaskFiveTests` | Validates `/balance` REST endpoint for various userIds |

---

## 👤 Author

**Jatin Jaiswal**
Java Developer | Backend Enthusiast
📍 Jaipur, India
📧 [jatinjaiswal673@gmail.com](mailto:jatinjaiswal673@gmail.com)
🧠 [LeetCode](https://leetcode.com/u/JatinJaiswal/)

---

## ⚠️ License

This project is built for educational purposes as part of the [Forage Virtual Internship](https://www.theforage.com/) and is not intended for production use.

```
