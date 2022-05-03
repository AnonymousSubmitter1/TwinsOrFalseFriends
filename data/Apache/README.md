# Apache httpd (energy)

## Case Study Information

- software: httpd-2.4.35 with apr-1.6.5 and apr-util-1.6.1
- cluster: zmiy (i5 only)
- benchmark/workload:
  - ApacheBench, Version 2.3, Revision 1826891 (compiled from httpd-2.4.35 with apr-1.6.5 and apr-util-1.6.1)
  - 100000 requessts (1000 concurrent)
  - static HTML file (2.1 KB)
- configurations: 4032
- properties:
  - performance (run time)
  - energy (energy consumption)
  - cpu (cpu load)
- fixed time: 600s = 10min (dynamic projection (60s))
- notes:
  - 5 repetitions
- configuration space constraints:
  - `not compression or not keepalive`
    - reason: application domain restriction
  - `not keepalive or not event`
    - reason: configurations with keepalive and event result in the benchmark client reporting failing requessts
  - `processCount * threadCount > 1000`
    - reason: server needs to be capable of processing 1000 concurrent requessts for this benchmark/workload

## Measurements Information

- average relative standard deviations:
  - performance: 5.96 %
  - benchmark-energy: 6.34 %
  - fixed-energy: 3.09 %
- relative standard deviations available in separate file
- 117 configurations with deviations > 10 %
  - 107 configurations with performance deivation > 10 %
  - 116 configurations with energy deviation > 10 %
