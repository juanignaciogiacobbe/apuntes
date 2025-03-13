# Distributed Architectures

## Shared Disk Architecture

### Advantages
- Relatively simple to manage.
- Single source of truth.

### Disadvantages
- Single point of failure.
- Bandwidth and network latency.
- Limited Scalability.

![[Snowflake/SnowPro Core COF-C02/img/Pasted image 20250203165629.png]]


## Shared Nothing Architecture

### Advantages
- Co-locating compute and storage avoids networking latency issues.
- Generally cheaper to build & maintain.
- Improved scaling over shared-disk architecture.

### Disadvantages
- Scaling still limited.
- Storage and compute tightly coupled.
- Tendency to overprovision.

![[Snowflake/SnowPro Core COF-C02/img/Pasted image 20250203165955.png]]