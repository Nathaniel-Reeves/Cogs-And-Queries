# ⚙️ Cogs & Queries
**The Industrial SQL Puzzle Engine**

Cogs & Queries is an interactive educational platform designed to teach SQL through gamified problem-solving. Users are challenged to "fix the machine" by writing precise SQL queries to retrieve specific datasets.

## 🎯 Project Goal
To bridge the gap between static SQL tutorials and real-world database management by providing a live, reactive sandbox environment where users get immediate feedback on their query logic.

## 🛠️ Tech Stack
*   **Database:** [Microsoft SQL Server](https://www.microsoft.com)
*   **Server-Side:** [PHP 8.x](https://www.php.net) (via PDO)
*   **Frontend:** [Bootstrap 5](https://getbootstrap.com), [jQuery](https://jquery.com)
*   **Data Display:** [jQuery DataTables](https://datatables.net)
*   **Branding:** [Google Fonts](https://fonts.google.com) (Russo One) & [Bootstrap Icons](https://icons.getbootstrap.com)

## 🚀 Core Features
*   **Interactive Workshop:** A split-screen UI for real-time query testing.
*   **The Steam Engine:** A backend validation logic that compares user results to hidden master keys.
*   **Progressive Mastery:** Three initial "Gears" (Levels) covering SELECT, WHERE, and JOIN operations.
*   **Live Feedback:** Instant syntax error reporting and success validation via AJAX.

## 📂 Project Structure
- `index.php` - Main game interface and UI.
- `check_query.php` - Backend validation logic.
- `db.php` - SQL Server connection configuration.
- `assets/` - Custom CSS/JS and branding assets.