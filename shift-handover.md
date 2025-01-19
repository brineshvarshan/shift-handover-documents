Shift Handover Report for Take My Tickets

1. Shift Information
- Shift Date: January 19, 2025
- Shift Time: 9:00 AM - 5:00 PM
- Person Completing Handover: M Brinesh Varshan
- Person Receiving Handover: Assinged TL
- Platform Status: Operational with minor issues, resolved during the shift.

----------------------------------------------------------------------------------------------------------------------------------------

2. Platform Health and Incident Management

System Health Overview:
- General Status: The platform is running smoothly without major outages. However, there was an incident with the payment gateway between 1:00 PM and 1:30 PM, which was resolved promptly.
- API Status: All APIs (event creation, ticket purchase, ticket validation) are operational. There were no issues with third-party services (payment gateway, email delivery).
- Database Performance: The MySQL database is performing well with no slow queries identified in Datadog.
- Infrastructure Health: Grafana and Datadog are both used to monitor server performance, including CPU, memory, and disk usage. No critical performance issues were flagged during the shift.

----------------------------------------------------------------------------------------------------------------------------------------

Incident(s) During Shift:

Incident 1: Payment Gateway Delay (Resolved)
- Time: 1:00 PM - 1:30 PM
- Issue: Payment gateway experienced intermittent delays due to rate-limiting issues with their API, resulting in delayed ticket purchases.
- Monitoring: Detected in Datadog through custom API latency dashboards showing a spike in response times for the payment gateway API. Grafana also provided insights into the impact of this delay on system performance, revealing increased response times for the ticket purchase endpoint.
- Resolution: Contacted the payment gateway support team, confirmed their issue, and adjusted rate-limiting thresholds to prevent further delays. Resolved and monitored through Datadog alerts.
- Status: Resolved.

Incident 2: High Traffic Load Performance Lag (Resolved)
- Time: 2:30 PM - 3:00 PM
- Issue: Latency spikes observed during the "Rock Concert" ticket sale. Some users experienced timeouts during peak traffic.
- Monitoring: Datadog triggered an alert for high API latency, where response times exceeded 500ms. Simultaneously, Grafana dashboards showed high server load during this period.
- Resolution: The platform’s auto-scaling function kicked in to adjust resources. Datadog’s auto-scaling integration ensured load balancers increased capacity automatically. Traffic normalized after 5 minutes.
- Status: Resolved and monitored for future incidents.

Outages or Service Disruptions:
- Email Delivery Delay: A 10-minute delay in ticket confirmation emails due to issues with the email delivery service. The issue was tracked using Datadog’s log aggregation tool, where errors were found in the email delivery pipeline.
- Resolution: Restarted the email service and Grafana was used to confirm the resolution by tracking real-time email logs and service status.

----------------------------------------------------------------------------------------------------------------------------------------

3. Ticket Sales & Orders

Total Tickets Sold:
- Event 1: "Paal Dabba First Live in Concert"
  - 500/1500 tickets sold
  - 3-hour peak during promotion.
  - Current Status: 1000 tickets remaining.
- Event 2: "PRABHU DEVA'S VIBE LIVE IN DANCE CONCERT"
  - 300/1000 tickets sold
  - No significant issues with this event.
- Event 3: "Abhishek Upmanyu LIVE 2025 - Chennai"
  - 1200/1500 tickets sold
  - Current Status: 300 tickets remaining.

Ticket Availability:
- Event 1: 1000 tickets available (high demand).
- Event 2: 700 tickets available.
- Event 3: 300 tickets available (low demand).

Refund Requests:
- Pending Refunds: 5 refund requests pending approval due to payment issues (card declines).
- Completed Refunds: 2 refunds processed for Event A customers who reported double charges.

Customer Service Queries:
- 10 customer service tickets received:
  - 3 requests regarding issues with payment failures during checkout.
  - 5 inquiries about event details, seating arrangements, and venue specifics.
  - 2 reports of missing ticket emails, which were promptly resolved by resending the confirmation emails.
  - Status: All issues resolved, and the customer service team has followed up with affected users.

----------------------------------------------------------------------------------------------------------------------------------------

4. Security and Fraud Monitoring

Suspicious Activity / Fraudulent Orders:
- Fraudulent Transactions:
  - 2 accounts flagged for high-risk fraud patterns due to multiple failed payment attempts.
  - 1 account flagged for chargeback activity after multiple successful ticket purchases were reversed.
  - Action Taken: Accounts were suspended, and fraud team was notified for further investigation. Fraud patterns were tracked in Datadog, which flagged spikes in failed payment attempts and correlated these with unusual account activity.

Account Suspensions / Bans:
- Account #12345 suspended due to a history of multiple fraudulent orders flagged by our automated fraud detection system. The fraud team will handle the appeal process.
- Account #67890 was reinstated after manual review of suspicious activity. No fraudulent behavior detected.

----------------------------------------------------------------------------------------------------------------------------------------

5. Pending Tasks & Follow-ups

Pending Tasks for Incoming Team:
- Investigate high traffic load during peak hours to ensure the system can handle future events with large volumes (possible load balancing adjustments).
- Process the 5 pending refund requests for Event A and B customers.
- Follow up with fraud team to review suspended accounts flagged for suspicious behavior.

Platform Updates / Maintenance:
- Upcoming Maintenance:
  - A scheduled maintenance window for tomorrow from 11:00 PM - 12:00 AM for platform optimization and minor bug fixes. This will include updates to the email delivery system to address slow delivery times.

Follow-up Items:
- Follow up on performance scaling settings during high-demand events (auto-scaling groups, load balancing, database optimization).
- Review payment gateway rate-limiting policies to avoid delays during future events.

----------------------------------------------------------------------------------------------------------------------------------------

6. General Remarks

General Observations:
- Overall, the system is stable, and most issues were resolved within a short time frame.
- High traffic during promotions continues to be a challenge for the platform. Scaling solutions should be tested further to ensure high availability during future ticket sales for major events.
- Fraud monitoring and ticket security continue to be priorities, especially for high-demand events like "Rock Concert."

Recommendations for Incoming Team:
- Monitor performance metrics closely for the next high-traffic events using Datadog’s APM (Application Performance Monitoring) and Grafana’s dashboards for real-time server and application insights.
- Keep an eye on user feedback regarding payment failures, as this may indicate problems with the checkout flow or payment gateway.
- Ensure all customer service inquiries are addressed in a timely manner to maintain user satisfaction.

----------------------------------------------------------------------------------------------------------------------------------------

7. Technical Considerations for the Incoming Team

System Monitoring:
- Continue monitoring system performance using Datadog for latency, error rates, and resource usage. Set up Grafana dashboards for visualizing key metrics and detecting trends in system health.
- Event Creation Process: Ensure no disruptions occur during event creation, especially if the event is large and involves high traffic.
- Load Balancer Configuration: Confirm that the auto-scaling settings for the load balancer are optimized for high-demand events, such as concert ticket sales.

----------------------------------------------------------------------------------------------------------------------------------------

Conclusion:
The shift has been relatively smooth, with some minor issues around payment gateway delays and high traffic performance. Both have been resolved promptly, and there are no major outages. The system is stable, and the incoming team should focus on scalability and fraud monitoring for the next high-traffic period.
