# 🛠️ Technical Design: Cogs & Queries

## 1. System Architecture
The application follows a **Client-Server-Database** model using asynchronous communication to ensure a "zero-refresh" gameplay experience.

### Data Flow
1. User inputs SQL string into the frontend `textarea`.
2. **jQuery** captures the input and sends an **AJAX POST** to the PHP backend.
3. **PHP** executes the string against **SQL Server** using a restricted user account.
4. Results are compared; a JSON response is returned to the client.
5. **DataTables** renders the resulting rows dynamically.

## 2. Technical Requirements
### Functional
- **Comparison Engine:** Must use `json_encode` comparison or row-by-row iteration to ensure the User's result set matches the Target's structure and data exactly.
- **Dynamic Grid:** The frontend table must use `destroy: true` in DataTables to allow for changing column headers between different queries.
- **Error Handling:** PHP `try-catch` blocks must capture `PDOException` and return the raw SQL Server error message to the UI for debugging.

### Non-Functional
- **Latency:** AJAX response time should be < 200ms for local queries.
- **Security:** The PHP backend must strictly use read-only database credentials to prevent accidental `DROP` or `DELETE` commands.
- **Responsive UI:** The layout must remain functional on screens as small as 768px (Tablet) using Bootstrap Grid.

## 3. Database Schema

| Table | Key Columns | Purpose |
| :--- | :--- | :--- |
| `Employees` | `ID, Name, Dept` | Level 1: Basic retrieval |
| `Products` | `ID, Name, Price` | Level 2: Numeric filtering |
| `Sales` | `SaleID, ProductID, Qty` | Level 3: Relational joins |

## 4. Engineering Milestones
1. **Milestone 1:** Establish SQL Server PDO connection and "Level 1" table setup.
2. **Milestone 2:** Implement AJAX query submission and basic DataTables rendering.
3. **Milestone 3:** Deploy JSON comparison logic and success/fail UI states.