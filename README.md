# aws-aurora-shailesh


https://aws.amazon.com/blogs/database/improve-application-availability-on-amazon-aurora/

In this example, the failover operation was initiated manually, which gives us the opportunity to measure client impact in a controlled manner. The test client’s operating system and networking setup don’t use DNS caching, and we put the following settings in the ~/.my.cnffile in order to make the test output more readable:

[mysql]
connect_timeout=1

[client]
user=USERNAME
password=PASSWORD
We run the shell command below to ping the writer endpoint every second, and report the instance role (writer or reader).

```

while true; do mysql -haurora-test.cluster-xxx.us-west-2.rds.amazonaws.com --batch --skip-column-names -e "select now(), if(@@innodb_read_only = 1, 'reader', 'writer')"; sleep 1; done;


```


Here's a utility list of AWS blogs relevant to Amazon Aurora, formatted as a GitHub README.md file:

# Amazon Aurora Blog Posts

A curated list of AWS blog posts about Amazon Aurora.

## Database Blog

### [Schedule jobs in Amazon RDS or Amazon Aurora PostgreSQL using pg_tle and pg_dbms_job](https://aws.amazon.com/blogs/database/schedule-jobs-in-amazon-rds-or-amazon-aurora-postgresql-using-pg_tle-and-pg_dbms_job/)
Demonstrates how to use Trusted Language Extensions (TLEs) for PostgreSQL to install and use pg_dbms_job on Amazon Aurora and Amazon RDS for sub-minute job scheduling.

### [Build a custom HTTP client in Amazon Aurora PostgreSQL and Amazon RDS for PostgreSQL: An alternative to Oracle's UTL_HTTP](https://aws.amazon.com/blogs/database/build-a-custom-http-client-in-amazon-aurora-postgresql-and-amazon-rds-for-postgresql-an-alternative-to-oracles-utl_http/)
Provides guidance on creating a custom HTTP client in PostgreSQL as an alternative to Oracle's UTL_HTTP package during migration.

### [Implement a rollback strategy after an Amazon Aurora MySQL blue/green deployment switchover](https://aws.amazon.com/blogs/database/implement-a-rollback-strategy-after-an-amazon-aurora-mysql-blue-green-deployment-switchover/)
Discusses steps for performing a blue/green deployment switchover and setting up a rollback strategy for Amazon Aurora MySQL.

### [Review your Amazon Aurora and Amazon RDS security configuration with Prowler's new checks](https://aws.amazon.com/blogs/database/review-your-amazon-aurora-and-amazon-rds-security-configuration-with-prowlers-new-checks/)
Explores new and expanded Amazon RDS security checks in Prowler for AWS, including integration with AWS Security Hub.

### [Migrate an on-premises MySQL database to Amazon Aurora MySQL over a private network using AWS DMS homogeneous data migration and Network Load Balancer](https://aws.amazon.com/blogs/database/migrate-an-on-premises-mysql-database-to-amazon-aurora-mysql-over-a-private-network-using-aws-dms-homogeneous-data-migration-and-network-load-balancer/)
Guides through the steps of performing a homogeneous migration from an on-premises MySQL database to Amazon Aurora MySQL using AWS DMS.

## Big Data Blog

### [Achieve near real time operational analytics using Amazon Aurora PostgreSQL zero-ETL integration with Amazon Redshift](https://aws.amazon.com/blogs/big-data/achieve-near-real-time-operational-analytics-using-amazon-aurora-postgresql-zero-etl-integration-with-amazon-redshift/)
Provides step-by-step guidance on getting started with near real-time operational analytics using Amazon Aurora PostgreSQL zero-ETL integration with Amazon Redshift.

### [Announcing data filtering for Amazon Aurora MySQL zero-ETL integration with Amazon Redshift](https://aws.amazon.com/blogs/big-data/announcing-data-filtering-for-amazon-aurora-mysql-zero-etl-integration-with-amazon-redshift/)
Introduces data filtering on zero-ETL integrations between Amazon Aurora MySQL and Amazon Redshift, allowing selective data replication.

### [Getting started guide for near-real time operational analytics using Amazon Aurora zero-ETL integration with Amazon Redshift](https://aws.amazon.com/blogs/big-data/getting-started-guide-for-near-real-time-operational-analytics-using-amazon-aurora-zero-etl-integration-with-amazon-redshift/)
Offers a guide to get started with near real-time operational analytics using Amazon Aurora zero-ETL integration with Amazon Redshift.

## AWS News Blog

### [Join the preview of Amazon Aurora Limitless Database](https://aws.amazon.com/blogs/aws/join-the-preview-of-amazon-aurora-limitless-database/)
Announces the preview of Amazon Aurora Limitless Database, supporting automated horizontal scaling for high-volume transactions and petabyte-scale data management.

This list provides a comprehensive overview of recent AWS blog posts related to Amazon Aurora, covering various aspects such as job scheduling, migration, security, operational analytics, and new features.

Citations:
[1] https://docs.aws.amazon.com/AmazonRDS/latest/AuroraUserGuide/CHAP_Tutorials.html
[2] https://aws.amazon.com/blogs/aws/category/database/amazon-aurora/
[3] https://www.projectpro.io/article/amazon-aurora/853
[4] https://www.percona.com/blog/when-should-i-use-amazon-aurora-and-when-should-i-use-rds-mysql/
[5] https://intellipaat.com/blog/what-is-aws-amazon-aurora/
[6] https://aws.amazon.com/blogs/big-data/category/database/amazon-aurora/
[7] https://tutorialsdojo.com/amazon-aurora/
[8] https://aws.amazon.com/blogs/database/category/database/amazon-aurora/
