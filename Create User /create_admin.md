To create an admin user in MySQL, you need to follow these steps:

1. **Create a New User:**
   Use the `CREATE USER` statement to create a new user. Specify the username and the host from which the user will connect. For an admin user, you typically want to grant access from localhost for security reasons.

   ```sql
   CREATE USER 'admin'@'localhost' IDENTIFIED BY 'password';
   ```

   Replace `'admin'` with your desired username and `'password'` with a strong password.

2. **Grant Administrative Privileges:**
   Admin users typically require administrative privileges to perform various tasks, such as creating databases, managing users, and executing administrative commands. You can grant all administrative privileges to the user using the `GRANT` statement with the `ALL PRIVILEGES` keyword.

   ```sql
   GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' WITH GRANT OPTION;
   ```

   The `WITH GRANT OPTION` allows the admin user to grant the privileges they have been granted to other users.

3. **Flush Privileges:**
   After granting privileges, use the `FLUSH PRIVILEGES` statement to apply the changes immediately.

   ```sql
   FLUSH PRIVILEGES;
   ```

4. **Secure Access:**
   It's essential to secure access to the admin account by limiting connections to trusted hosts and using strong, unique passwords.

5. **Documentation:**
   Document the admin username, password, and privileges for future reference and auditing purposes.

By following these steps, you can create an admin user with administrative privileges in MySQL. This user will have the necessary authority to manage databases, users, and other aspects of your MySQL server. Make sure to follow security best practices to protect your database environment.
