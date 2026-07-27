---
layout: page
title: About Packablock
permalink: /about/
---

# About Packablock

Packablock was founded on a simple premise: **the modern software supply chain is inherently untrusted, and retroactive security alerts are too late.**

Every day, developers and automated CI/CD pipelines pull millions of open-source packages from public registries. Traditional tools monitor these dependencies in a passive, "awareness-first" posture—scanning lockfiles after they are committed and alerting security teams when a vulnerability is published in a CVE database. 

However, studies show that over 50% of malicious packages execute their payloads immediately upon installation. Receiving an alert hours or days later means your build environments or developer workstations are already compromised.

Packablock transitions the supply chain to a **preventative, zero-trust security model**. By generating cryptographically signed, sequential timeline logs of dependency modifications, Packablock acts as a continuous validation gate. If a dependency is modified, tampered with, or updated without validation, Packablock blocks the build before it can reach compile time.

## Our Mission

We are building the open-source tooling needed to achieve compliance with modern supply chain standards (such as **SLSA Build L3** and **Sigstore** signing) without requiring complex, proprietary enterprise control systems. Packablock is built for developers, SecOps engineers, and autonomous agent systems who require deterministic software integrity.

---

### Get in Touch

If you are interested in deploying private registry instances, collaborating on the Continuous Attestation specification, or contributing to the CLI clients, please reach out:

* **Email**: [support@packablock.com](mailto:support@packablock.com)
* **LinkedIn**: [Aaron Bronow](https://www.linkedin.com/in/aaronbronow)
* **GitHub**: [Packablock Organization](https://github.com/Packablock)
