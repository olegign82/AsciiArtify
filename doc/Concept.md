# AsciiArtify
---


|                                     | minikube                                                          | k3d                                                                 | kind                                                                                 |
|-------------------------------------|-------------------------------------------------------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| Infrastructure and Networking       | Linux, Bash, TCP/IP, DNS, Load Balancers                          | Advanced networking tools like F5, Citrix, Cloudflare, etc.         | Advanced networking tools like Cisco, Juniper, and Arista                            |
| Troubleshooting                     | Nagios, Zabbix, ELK Stack, Prometheus, Grafana                    | Advanced log analysis tools like Splunk, Graylog, or Loggly         | Advanced log analysis tools like Datadog, New Relic, or AppDynamics                  |
| Cloud Computing and Virtualization  | AWS, GCP, Azure, VirtualBox, Docker, Kubernetes                   | Advanced cloud infrastructure tools like Terraform, Puppet, or Chef | Advanced cloud infrastructure tools like CloudFormation, ARM templates, or SaltStack |
| Distributed Systems and Scalability | Apache Kafka, RabbitMQ, Redis, HAProxy, Nginx                     | Advanced distributed systems tools like Cassandra, Hadoop, or Spark | Advanced distributed systems tools like Kubernetes Operators, Istio, or Linkerd      |
| Security and Compliance             | Security best practices, firewalls, encryption, SSL/TLS           | Advanced security tools like Nessus, Qualys, or OpenVAS             | Advanced security tools like HashiCorp Vault, AWS KMS, or Azure Key Vault            |
| Leadership and Communication        | Collaboration tools, Agile                                        | Project management tools, team building skills                      | Interpersonal skills, communication skills, mentoring skills                         |
| Soft Skills                         | Problem-solving, critical thinking, time management, adaptability | Decision-making, conflict resolution, emotional intelligence        | Leadership, teamwork, creativity, innovation, negotiation                            |
| Hard Skills                         | Python, Go, Java, C++, Bash, PowerShell                           | Perl, Ruby, PHP, Node.js, Scala, Rust                               | terraform, ansible, vault, Prometheus, grafana, ubuntu, debian, rethat               |



The list of commands to create k3d cluster and deploy custom hello-world container:

```
k3d cluster create demo
k create deploy demo --image olegign82/demo:v1.0.1
k get po -w
k port-forward deploy/demo 8080
```

![Image](../.data/demo.gif)


Test from another terminal window before starting k3d cluster and after (response received):

```
curl 127.0.0.1:8080
```

![Image](../.data/demo1.gif)


Conclusion:
---

Consiring all the tools (minikube, k3d and kind) are very close in nature and suitable for our needs, there is no big difference which one to use.
The suggestion was to use k3d due to it being the most lightweighted solution, an easy one and also the one we have experience with.
