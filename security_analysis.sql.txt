-- Security Operations Dashboard SQL Analysis

-- These queries support KPIs and visuals in Power BI Security Operations Dashboard

USE security_ops;

-- Total login attempts
SELECT COUNT(*) AS total_logins
FROM login_logs;

-- Total failed logins
SELECT COUNT(*) AS failed_logins
FROM login_logs
WHERE login_status = 'Failed';

-- Failed login percentage
SELECT 
ROUND(
(SUM(CASE WHEN login_status = 'Failed' THEN 1 ELSE 0 END) / COUNT(*)) * 100, 2
) AS failed_login_percentage
FROM login_logs;

-- Failed vs successful logins
SELECT login_status, COUNT(*) AS total
FROM login_logs
GROUP BY login_status;

-- Top 10 risky users
SELECT user_id, COUNT(*) AS failed_attempts
FROM login_logs
WHERE login_status = 'Failed'
GROUP BY user_id
ORDER BY failed_attempts DESC
LIMIT 10;

-- Top 10 risky IP addresses
SELECT ip_address, COUNT(*) AS failed_attempts
FROM login_logs
WHERE login_status = 'Failed'
GROUP BY ip_address
ORDER BY failed_attempts DESC
LIMIT 10;

-- Country-wise login attempts
SELECT country, COUNT(*) AS total_attempts
FROM login_logs
GROUP BY country
ORDER BY total_attempts DESC;

-- Login activity over time
SELECT date, COUNT(*) AS attempts
FROM login_logs
GROUP BY date
ORDER BY date;

-- Hour vs Day failed login analysis
SELECT day, hour, COUNT(*) AS failed_attempts
FROM login_logs
WHERE login_status = 'Failed'
GROUP BY day, hour
ORDER BY day, hour;

-- Late night login risk
SELECT 
CASE 
    WHEN late_night_login = 1 THEN 'Late Night'
    ELSE 'Normal Hours'
END AS login_time_type,
COUNT(*) AS total_attempts
FROM login_logs
GROUP BY late_night_login;
