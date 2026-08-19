IVR Panel with Client, Reseller and Admin User roles

![alt text](/screen1.png?raw=true)
![alt text](/screen2.png?raw=true)
![alt text](/screen3.png?raw=true)
![alt text](/screen4.png?raw=true)
![alt text](/screen5.png?raw=true)

IVR Panel Modules

Client

    Dashboard
    Logs
        Inbound
        outbound
        SMS
    Agents
    Call Settings
        IVR setting
        Source Number Setting
        SMS Configuration
        API Docs
    Reports
        Calls
        Agents
        Billing
    CRM

Admin

    Dashbpard
    List User
        Edit user
        Manager User permissions
        Manage Plans
        Manage User Source / DID Numbers
        Disable / Inactive User
        Add / Remove Call and SMS Credits
    New user
    Call Logs
        Inbound/Outbound
        OBD Logs
        SMS Logs
        Email logs
    Manage Agents
    Reports
        Client Summary Report
        Client Billing Report


## Installation

Install Git first if it is not already available:

```bash
# Ubuntu / Debian
sudo apt update
sudo apt install -y git

# Verify Git
 git --version
```

Clone the public repository and install the Laravel application:

```bash
git clone https://github.com/ekycsoftcents-hash/ivr-panel-laravel12-php84.git
cd ivr-panel-laravel12-php84

composer install --no-dev --optimize-autoloader
cp .env.example .env
php artisan key:generate
```

Configure the database, mail, AWS, telephony, and other service values in `.env`, then run:

```bash
php artisan migrate --force
php artisan storage:link
php artisan optimize
```

For frontend assets, use:

```bash
npm install
npm run production
```

The web server document root must point to the project's `public` directory. Laravel 12 requires PHP 8.2 or newer; PHP 8.4 is supported by this project.

For the complete migration details, see [LARAVEL12_MIGRATION.md](LARAVEL12_MIGRATION.md).

## Git update workflow

After making changes, push them to the public repository with:

```bash
git add .
git commit -m "Describe your changes"
git push origin main
```

