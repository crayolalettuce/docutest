1. Criteo - /feeds/products/criteo
1. Sales - /feeds/sales
1. Sailthru recommendation - /feeds/sailthru_recommendations
1. Product recommendations - /feeds/product_recommendations
1. Google Analytics data feed - crontab: 30 12,19 * * * $CONSOLE google_analytics_data >> $TMP_LOGS/google_analytics_data.log 2>&1