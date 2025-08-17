# Banking System - CQRS & Domain-Driven Design

A full-stack banking application demonstrating **Domain-Driven Design (DDD)** and **Command Query Responsibility Segregation (CQRS)** with event sourcing.

## Architecture Overview

### Backend (Spring Boot)
- **Domain Layer**: Contains aggregates, domain events, and business logic
- **Command Side**: Handles write operations (state changes)
- **Query Side**: Handles read operations (projections)
- **Event Store**: Persists domain events for event sourcing
- **CQRS**: Separate command and query models

### Frontend (Next.js)
- **Modern React**: Built with Next.js 14 and TypeScript
- **Responsive UI**: Tailwind CSS for styling
- **API Integration**: RESTful communication with backend
- **Real-time Updates**: Automatic refresh after operations

## Key Concepts Implemented

### 1. Domain-Driven Design (DDD)
- **Aggregates**: `BankAccountAggregate` encapsulates business logic
- **Domain Events**: Capture state changes (`AccountOpened`, `FundsDeposited`, etc.)
- **Value Objects**: Immutable objects representing domain concepts
- **Repository Pattern**: Abstraction for data persistence

### 2. Command Query Responsibility Segregation (CQRS)
- **Command Side**: Write operations through command handlers
- **Query Side**: Read operations through separate read models
- **Separate Databases**: Commands and queries use different optimized models

### 3. Event Sourcing
- **Event Store**: All state changes stored as events
- **Event Replay**: Aggregates rebuilt from event history
- **Audit Trail**: Complete history of all operations
- **Temporal Queries**: Query state at any point in time

## Project Structure

```
banking-app/
├── backend/                    # Spring Boot Application
│   ├── src/main/java/com/example/bank/
│   │   ├── domain/            # Domain Layer
│   │   │   ├── BankAccountAggregate.java
│   │   │   └── event/         # Domain Events
│   │   ├── command/           # Command Side (Write)
│   │   │   ├── dto/           # Command DTOs
│   │   │   ├── service/       # Command Services
│   │   │   └── controller/    # Command Controllers
│   │   ├── query/             # Query Side (Read)
│   │   │   ├── model/         # Read Models
│   │   │   ├── dto/           # Query DTOs
│   │   │   ├── service/       # Query Services
│   │   │   └── controller/    # Query Controllers
│   │   ├── infrastructure/    # Infrastructure Layer
│   │   │   └── EventStore*    # Event Storage
│   │   └── repository/        # Data Access
│   └── resources/
│       └── application.yml    # Configuration
├── frontend/                  # Next.js Application
│   ├── app/
│   │   ├── components/       # React Components
│   │   ├── page.tsx         # Main Dashboard
│   │   └── layout.tsx       # App Layout
│   ├── lib/
│   │   └── api.ts           # API Service Layer
│   ├── types/
│   │   └── account.ts       # TypeScript Types
│   └── [config files]       # Next.js Configuration
└── README.md
```

## Features

### Account Management
- ✅ **Create Account**: Open new bank accounts with initial balance
- ✅ **Deposit Funds**: Add money to existing accounts
- ✅ **Withdraw Funds**: Remove money from accounts (with balance validation)
- ✅ **View Balance**: Query current account balance and details
- ✅ **Account History**: Complete audit trail through event sourcing

### Domain Events
The system emits the following domain events:
- `AccountOpened` - When a new account is created
- `FundsDeposited` - When money is added to an account
- `FundsWithdrawn` - When money is removed from an account
- `AccountClosed` - When an account is deactivated
- `TransferInitiated` - When a transfer between accounts starts
- `TransferCompleted` - When a transfer is successfully completed
- `TransferFailed` - When a transfer fails

### Validation & Business Rules
- ✅ Initial balance must be non-negative
- ✅ Withdrawal amount cannot exceed current balance
- ✅ Deposit and withdrawal amounts must be positive
- ✅ Account holder name is required
- ✅ Only active accounts can perform transactions

## Getting Started

### Prerequisites
- **Java 17+**
- **Node.js 18+**
- **Maven 3.6+**
- **npm/yarn**

### Backend Setup (Spring Boot)

1. **Navigate to backend directory**:
   ```bash
   cd backend/
   ```

2. **Install dependencies**:
   ```bash
   mvn clean install
   ```

3. **Run the application**:
   ```bash
   mvn spring-boot:run
   ```

4. **Access H2 Console** (optional):
   - URL: http://localhost:8080/h2-console
   - JDBC URL: `jdbc:h2:mem:bankingdb`
   - Username: `sa`
   - Password: `password`

The backend API will be available at: `http://localhost:8080`

### Frontend Setup (Next.js)

1. **Navigate to frontend directory**:
   ```bash
   cd frontend/
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Run development server**:
   ```bash
   npm run dev
   ```

The frontend will be available at: `http://localhost:3000`

## API Endpoints

### Command Endpoints (Write Operations)
```http
POST /api/commands/accounts/open
POST /api/commands/accounts/deposit  
POST /api/commands/accounts/withdraw
```

### Query Endpoints (Read Operations)
```http
GET  /api/queries/accounts
GET  /api/queries/accounts/{accountId}
```

### Example API Calls

**Create Account**:
```bash
curl -X POST http://localhost:8080/api/commands/accounts/open \
  -H "Content-Type: application/json" \
  -d '{"accountHolder": "John Doe", "initialBalance": 1000.00}'
```

**Deposit Funds**:
```bash
curl -X POST http://localhost:8080/api/commands/accounts/deposit \
  -H "Content-Type: application/json" \
  -d '{"accountId": "ACC-123", "amount": 500.00}'
```

**Get Account**:
```bash
curl http://localhost:8080/api/queries/accounts/ACC-123
```

## Technologies Used

### Backend
- **Spring Boot 3.2** - Application framework
- **Spring Data JPA** - Data persistence
- **H2 Database** - In-memory database for development
- **Maven** - Dependency management
- **Java 17** - Programming language

### Frontend
- **Next.js 14** - React framework
- **TypeScript** - Type-safe JavaScript
- **Tailwind CSS** - Utility-first CSS framework
- **React Hooks** - State management

## Key Design Patterns

### 1. Aggregate Pattern
```java
public class BankAccountAggregate {
    // Encapsulates business logic and invariants
    // Emits domain events on state changes
    // Maintains consistency boundaries
}
```

### 2. Command Pattern
```java
public class DepositCommand {
    private String accountId;
    private BigDecimal amount;
    // Represents intention to change state
}
```

### 3. Repository Pattern
```java
public interface BankAccountRepository extends JpaRepository<BankAccount, String> {
    // Abstraction for data access
}
```

### 4. Event Sourcing Pattern
```java
public class EventStoreEntity {
    // Stores events instead of current state
    // Enables event replay and temporal queries
}
```

## Future Enhancements

### Planned Features
- [ ] **Account Transfers**: Transfer funds between accounts
- [ ] **Transaction History**: Detailed transaction logs
- [ ] **Account Types**: Checking, Savings, etc.
- [ ] **Interest Calculation**: Automated interest accrual
- [ ] **Notifications**: Real-time event notifications
- [ ] **Authentication**: User login and security
- [ ] **Multi-Currency**: Support for different currencies

### Technical Improvements
- [ ] **Event Bus**: Asynchronous event processing
- [ ] **Snapshots**: Optimize aggregate rebuilding
- [ ] **CQRS Projections**: Automated read model updates
- [ ] **Microservices**: Split into smaller services
- [ ] **Container Deployment**: Docker and Kubernetes
- [ ] **Monitoring**: Observability and metrics

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

For questions or support, please open an issue in the repository.