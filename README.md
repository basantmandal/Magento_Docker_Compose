# Magento Docker Compose - Local Magento Setup / Test Environment

## Introduction

This Docker Compose configuration is designed to create a local development environment for Magento 2. It provides a quick and easy way to set up Magento with PHP, MySQL, OpenSearch, Redis, and other necessary components in Docker containers. It also included MailHog for Email Testing.

## Setup

1. **Rename the `.env_magento2xx` file**

    Rename the `.env_magento2xx` file to match your desired Magento version. For example, if you're using Magento 2.4.7, rename `.env_magento247` to `.env`.

2. **Start the Docker containers**

    Run the following command to build and start the Docker containers:

    ```sh
    sh docker-compose up --build
    ```

3. **Access the PHP-FPM container**

    To get shell access to the PHP-FPM container, run:

    ```sh
    sh docker exec -it Mage247-PHP-FPM bash
    ```

4. **Download Magento**

    A sample download script (`download_magento247.sh`) is provided to help you download the Magento installation files. Run the script to download Magento.

5. **Run Magento Installation**

    Once the Magento installation files are downloaded, use the provided installation script (`install_magento247.sh`) to set up Magento.

---

## Magento Installation Commands

### 1. Create a Magento project

Replace `2.4.7` with the version of Magento you want to install:

```sh
composer create-project --repository-url=https://repo.magento.com/ magento/project-enterprise-edition=2.4.7 .
```

### 2. Install Magento Setup

Run the Magento installation command. Replace `magento247` with your desired Magento version (do not include any suffix like `p1`).

```sh
php bin/magento setup:install \
  --base-url="http://magentolocal.docker/" \
  --db-host="localhost" \
  --db-name="magento247" \
  --db-user="admin" \
  --db-password="admin" \
  --admin-firstname="admin" \
  --admin-lastname="user" \
  --admin-email="admin@example.com" \
  --admin-user="admin" \
  --admin-password="Admin123" \
  --language="en_US" \
  --currency="USD" \
  --timezone="America/Chicago" \
  --use-rewrites="1" \
  --backend-frontname="admin" \
  --search-engine="elasticsearch7" \
  --elasticsearch-host="opensearch" \
  --elasticsearch-port=9200
```

### 3. Install Sample Data

After the installation completes, run the following commands to install the sample data:

```sh
bin/magento sampledata:deploy && bin/magento setup:upgrade
```

### 4. Access Your Store

Once steps 2 and 3 are completed, you can browse your Magento store at:  
**[http://magentolocal.docker](http://magentolocal.docker)**

---

## Opensearch

OpenSearch is set as the default search engine for this project. It runs within the Docker environment and is configured automatically during installation.

## Mailhog

Mailhog is configured for email testing. You can view emails sent by Magento at:  
**[http://magentolocal.docker:8025](http://magentolocal.docker:8025)**

---

## 📫 Support

For support or any bug report or changes mail me at - <support@hashtagkitto.co.in>

## 🐞 Bug Report

Please open an [issue](https://github.com/basantmandal/Magento_Docker_Compose/issues) on GitHub.

When filing a bug remember that the better written the bug is, the more likely it is to be fixed.

You can also reach us at <support@hashtagkitto.co.in>

## 🍰 Contribution Guidelines 💖

Contributions are welcome! If you’d like to contribute to this project:

-   Fork the repository.
-   Create a new branch (git checkout -b feature/your-feature-name).
-   Make your changes and commit them (git commit -am 'Add new feature').
-   Push to the branch (git push origin feature/your-feature-name).
-   Open a pull request.

**Please Note** :- I may be a bit delayed in responding or slow in responding due to low amount of free time. I apologize for the inconvenience and I appreciate your patience

## 🤝 Consent

By using any Product/Module/Application/Docker Image/Container/compose, etc from Basant Mandal A.K.A (HK2 - Hash Tag Kitto), you hereby consent to our disclaimer and agree to its terms.

## 📢 Disclaimer

> **Basant Mandal (HK2 - Hash Tag Kitto)** does not make any warranties about the completeness, reliability and accuracy of this image or its related products. Any action you take upon the information you find here is strictly at your own risk.

> **Basant Mandal (HK2 - Hash Tag Kitto)** will not be liable for any losses and/or damages in connection with the use of our website.

## 💖Like my work? Help Us

Please rate my project or give some stars at [https://github.com/basantmandal/Magento_Docker_Compose/stargazers](https://github.com/basantmandal/Magento_Docker_Compose/stargazers). You can also contribute to make my Open Source Contribution more frequent and help others - [https://www.buymeacoffee.com/basantmandal](https://www.buymeacoffee.com/basantmandal) or [https://www.basantmandal.in/buymecoffee](https://www.basantmandal.in/buymecoffee)

## 📫 Feedback

If you have any feedback, please reach out to us at <support@hashtagkitto.co.in>

## 🔗 Links:

Feel free to reach me through the below handles if you'd like to contact me.

[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://www.basantmandal.in/)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/basantmandal/)
