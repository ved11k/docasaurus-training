# Sample Installation Guide for Banking Software

**Document Version:** 1.0
**Purpose:** Guide for installing a banking application on a Windows server (sample template).

## 1. System Requirements

| Component | Minimum Requirement |
|---|---|
| OS | Windows Server 2019/2022 |
| CPU | 4 Cores |
| RAM | 8 GB |
| Storage | 100 GB free |
| Database | Oracle 19c / SQL Server 2019 |
| Java | JDK 17 |
| Network | Static IP with LAN access |

## 2. Pre-Installation Checklist

- [ ] Administrator access available
- [ ] Database server installed and reachable
- [ ] Antivirus exclusions configured
- [ ] Application installer downloaded
- [ ] Backup of existing data completed
- [ ] SSL certificate available

## 3. Installation Steps

### Step 1: Create Installation Folder

```text
C:\BankingApp\
```

### Step 2: Install Java

1. Run the JDK installer.
2. Accept the license.
3. Install to:

```text
C:\Program Files\Java\jdk-17
```

4. Verify:

```cmd
java -version
```

### Step 3: Configure Database

Create a database named **BANKDB**.

Create an application user:

| Setting | Value |
|---|---|
| Username | bank_app |
| Password | ******** |
| Role | db_owner |

### Step 4: Install Banking Application

1. Right-click `BankingSetup.exe`.
2. Select **Run as Administrator**.
3. Choose installation path:

```text
C:\BankingApp\
```

4. Click **Install**.

### Step 5: Configure Application

Edit:

```text
C:\BankingApp\config\application.properties
```

Example:

```properties
db.host=192.168.1.10
db.port=1521
db.name=BANKDB
db.user=bank_app
db.password=YourPassword
server.port=8080
```

### Step 6: Start Services

```cmd
net start BankingApp
```

## 4. Verification

| Test | Expected Result |
|---|---|
| Login page opens | Success |
| Database connection | Connected |
| User authentication | Working |
| Transaction module | Accessible |

## 5. Troubleshooting

| Issue | Solution |
|---|---|
| Cannot connect to DB | Verify IP, port, and credentials |
| Service won't start | Check Windows Event Viewer |
| Login page not loading | Confirm port 8080 is open |
| Slow performance | Increase JVM memory and RAM |

## 6. Security Recommendations

- Change default passwords immediately.
- Enable HTTPS using a valid SSL certificate.
- Restrict database access to application servers only.
- Perform daily database backups.
- Keep the operating system and banking software updated.

Additional notes

---

**Note:** This is a generic sample installation guide for demonstration and documentation purposes.

Link [Getting Started](/docs/getting-started.md)
