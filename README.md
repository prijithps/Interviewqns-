# Interviewqns-
```text
1. Kubernetes pods are Running, but app is down. What does it indicate?

Answer:
Pods being in "Running" state only means the container process started successfully. It does not guarantee the application is functioning properly. Possible issues include:
- Application crash inside container
- Readiness/liveness probe failures
- Service or ingress misconfiguration
- Database/backend connectivity issues
- Port mismatch
- Network policy blocking traffic
- Application returning errors despite container running

------------------------------------------------------------

2. Jenkins pipeline succeeded, but deployment failed. How is that possible?

Answer:
Jenkins success only confirms pipeline steps executed without errors. Deployment can still fail because:
- Kubernetes deployment rollout failed after pipeline completion
- Application startup failure
- Incorrect image tag deployed
- Insufficient cluster resources
- Configuration or secret issues
- Post-deployment health checks failed
- Deployment approval/manual step skipped

------------------------------------------------------------

3. Docker container healthy, but users cannot access application. Why?

Answer:
Container health only checks internal process health. External access may fail due to:
- Incorrect port mapping
- Firewall/security group restrictions
- Load balancer issues
- DNS problems
- Reverse proxy misconfiguration
- Application listening on localhost instead of 0.0.0.0
- Network routing issues

------------------------------------------------------------

4. Monitoring dashboards show green, but customers report failures. What next?

Answer:
This usually indicates monitoring gaps. Next steps:
- Verify real user experience
- Check synthetic monitoring
- Analyze application logs
- Validate API responses
- Check latency and error rates
- Review recent deployments
- Verify third-party dependencies
- Compare business metrics vs infrastructure metrics

------------------------------------------------------------

5. Terraform apply successful, but infrastructure partially broken. Why?

Answer:
Terraform success means desired configuration was applied, not that application functionality works. Causes include:
- Incorrect Terraform code
- Cloud provider eventual consistency
- Manual changes outside Terraform
- Missing dependencies
- IAM permission issues
- Misconfigured networking
- Unsupported runtime conditions

------------------------------------------------------------

6. Application works in staging but fails in production. What could be different?

Answer:
Possible differences:
- Environment variables
- Secrets/configurations
- Traffic load
- Database size/data quality
- External integrations
- Network policies
- Authentication systems
- Resource limits
- Different Kubernetes versions
- DNS or SSL configurations

------------------------------------------------------------

7. CPU usage normal, but application response time very high. Why?

Answer:
High latency may be caused by:
- Database bottlenecks
- Slow external APIs
- Disk I/O delays
- Thread blocking
- Memory contention
- Garbage collection pauses
- Network latency
- Deadlocks
- Connection pool exhaustion

------------------------------------------------------------

8. Auto Scaling triggered correctly, but performance still poor. What bottleneck may exist?

Answer:
Scaling application instances may not solve:
- Database bottlenecks
- Shared storage limitations
- Network saturation
- Cache bottlenecks
- Load balancer limitations
- Application locking/contention
- Slow downstream services
- Message queue backlog

------------------------------------------------------------

9. Rollback completed successfully, but issue still continues. What does it mean?

Answer:
This indicates the deployment was probably not the root cause. Possible reasons:
- Infrastructure issue
- Database corruption
- Cache poisoning
- External dependency failure
- DNS propagation issue
- Persistent configuration issue
- Stateful component problem
- Monitoring false assumptions

------------------------------------------------------------

10. DNS working internally but not externally. What will you verify?

Answer:
Verify:
- Public DNS records
- DNS propagation
- Firewall rules
- NAT gateway configuration
- Public IP assignment
- Load balancer exposure
- Domain registrar settings
- TTL values
- Split-horizon DNS configuration

------------------------------------------------------------

11. SSL certificate valid, but HTTPS still failing. Why?

Answer:
Possible reasons:
- TLS version mismatch
- Incorrect certificate chain
- Expired intermediate certificate
- Reverse proxy misconfiguration
- Port 443 blocked
- SNI issues
- Cipher suite incompatibility
- Application not listening on HTTPS

------------------------------------------------------------

12. Kubernetes ingress configured properly, but traffic blocked. What else can fail?

Answer:
Possible failures:
- Service misconfiguration
- Pod readiness failure
- Network policies
- Ingress controller issue
- Firewall/security groups
- DNS mapping issue
- TLS termination problems
- Backend timeout settings
- Cloud load balancer health checks

------------------------------------------------------------

13. Logs available, but root cause still unclear. What additional data is needed?

Answer:
Additional data needed:
- Metrics
- Distributed tracing
- Network packet analysis
- Infrastructure events
- Deployment history
- User activity patterns
- System resource utilization
- Database performance metrics
- Correlation IDs across services

------------------------------------------------------------

14. CI/CD pipeline fast, but deployments unstable. What process issue exists?

Answer:
Possible process issues:
- Insufficient testing
- No rollback validation
- Weak release strategy
- Lack of canary/blue-green deployment
- Poor change management
- Missing monitoring gates
- Inadequate environment parity
- Skipping quality checks for speed

------------------------------------------------------------

15. Terraform state correct, but cloud resources drifted. How?

Answer:
Resource drift can occur because:
- Manual cloud console changes
- External automation modified resources
- Auto-scaling altered infrastructure
- Cloud provider updates
- Resources deleted outside Terraform
- State file outdated
- Partial apply failures

------------------------------------------------------------

16. Redis cache healthy, but app still slow. Why?

Answer:
Possible reasons:
- Low cache hit ratio
- Database still overloaded
- Poor cache strategy
- Large payload serialization delays
- Network latency to Redis
- Application-side bottleneck
- Blocking operations
- Inefficient queries

------------------------------------------------------------

17. Kafka brokers healthy, but consumer lag increasing. What could cause it?

Answer:
Possible causes:
- Slow consumers
- Message processing delays
- Consumer scaling insufficient
- Partition imbalance
- Downstream dependency slowdown
- Large message sizes
- Consumer rebalancing issues
- High producer throughput

------------------------------------------------------------

18. Nginx healthy, but backend services overloaded. Why?

Answer:
Nginx may function correctly while:
- Too much traffic reaches backend
- Load balancing inefficient
- Rate limiting absent
- Backend autoscaling insufficient
- Long-running requests accumulate
- Connection pooling misconfigured
- Backend resource exhaustion occurs

------------------------------------------------------------

19. Alerts triggered late during outage. What monitoring mistake exists?

Answer:
Possible monitoring mistakes:
- Alert thresholds too high
- Long evaluation intervals
- Missing real-user monitoring
- No predictive alerting
- Dependency monitoring absent
- Poor dashboard coverage
- Alert fatigue leading to muted alerts
- Only infrastructure monitored, not application behavior

------------------------------------------------------------

20. What is your approach when "everything looks healthy" but production is failing?

Answer:
My approach:
1. Verify actual customer impact
2. Compare healthy metrics vs business failures
3. Check recent deployments/changes
4. Validate dependencies (DB, APIs, DNS, cache)
5. Review logs, traces, and metrics together
6. Test end-to-end user flows
7. Check network connectivity and latency
8. Correlate timelines across systems
9. Investigate hidden bottlenecks
10. Avoid assumptions based only on dashboard status

Key Principle:
"Healthy infrastructure does not always mean healthy application behavior."
```
