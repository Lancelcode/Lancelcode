```
██████╗      ██╗██╗██████╗ ██╗   ██╗    ███████╗ ██████╗ ██╗    ██╗
██╔══██╗     ██║██║██╔══██╗╚██╗ ██╔╝    ██╔════╝██╔═══██╗██║    ██║
██║  ██║     ██║██║██████╔╝ ╚████╔╝     ███████╗██║   ██║██║ █╗ ██║
██║  ██║██   ██║██║██╔══██╗  ╚██╔╝      ╚════██║██║   ██║██║███╗██║
██████╔╝╚█████╔╝██║██████╔╝   ██║       ███████║╚██████╔╝╚███╔███╔╝
╚═════╝  ╚════╝ ╚═╝╚═════╝    ╚═╝       ╚══════╝ ╚═════╝  ╚══╝╚══╝
```

<div align="center">

**Systems, backend and security engineering · Understand the machine, then build the tools**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/djiby-sow-rebollo/)
[![Website](https://img.shields.io/badge/Website-djibysow.com-111111?style=for-the-badge&logo=googlechrome&logoColor=white)](https://djibysow.com/)
![Profile Views](https://komarev.com/ghpvc/?username=Lancelcode&color=6db33f&style=flat-square&label=Profile+Views)

</div>

---

## `$ whoami`

```json
{
  "name"       : "Djiby Sow Rebollo",
  "role"       : "Software Engineering student → Systems & Security Engineer",
  "university" : "Edinburgh Napier University",
  "location"   : "Edinburgh, Scotland",
  "focus"      : ["Systems", "Backend", "Security", "Performance / HPC", "AI/ML engineering"],
  "learning"   : ["Python at depth", "Mojo & SIMD", "Applied cryptography", "AI/ML engineering"],
  "available"  : "Junior engineering roles from late 2026",
  "principle"  : "Understand the machine. Don't just use the tools, build them."
}
```

---

## `$ ls projects/featured/`

### ⚡ mojo-bench &nbsp;·&nbsp; How fast is Mojo, really?
> *Same machine, same inputs, correctness checked before any timing is reported.*

Benchmarks **Mojo** against pure Python, NumPy, C and C with OpenMP across eight classic kernels (matrix multiply, n-body, Mandelbrot, reductions, hash tables, word counting). It also measures thread scaling and places the kernels on a roofline built from the machine's measured limits.

- Mandelbrot: Mojo's explicit SIMD is **4.3× faster than C** on one core, where idiomatic C does not vectorise
- Same algorithm, same code shape: Mojo and C run at the same speed, so the gap is about SIMD, not magic
- Every claim is reproducible with `make bench`, and the write-up says where Mojo does *not* win

`Mojo` `Python` `NumPy` `C` `OpenMP` `Benchmarking` `Roofline Analysis` `GitHub Actions`

[Repository](https://github.com/Lancelcode/mojo-bench) · [Results](https://github.com/Lancelcode/mojo-bench/tree/main/results) · [Write-up](https://github.com/Lancelcode/mojo-bench/blob/main/docs/writeup.md)

---

### 🗄️ PulseDB &nbsp;·&nbsp; Redis-compatible database server from scratch
> *Built to understand what happens between a socket and a data structure.*

An in-memory key-value server written in **C99** with **no third-party libraries**. It speaks the Redis wire protocol (RESP), so `redis-cli` works against it, and it supports strings, lists, hashes, sorted sets, streams, geo, and `MULTI`/`EXEC`. Replies for the supported commands were checked against Redis 7.

- Single-threaded event loop on non-blocking sockets, with lazy key expiry and no background thread
- Bounds-checked, restartable RESP parser; tests run under AddressSanitizer and UBSan on GCC and Clang
- Profiling-driven optimisation: a hash-indexed sorted set made `ZSCORE` **280× faster** in the store benchmark, and pipelined `GET` throughput rose about **5×**
- Honest limits are documented: no persistence on write, no auth or replication yet

`C` `Systems Design` `Networking` `RESP` `Data Structures` `Docker` `CI`

[Repository](https://github.com/Lancelcode/PulseDB) · [Architecture and design decisions](https://github.com/Lancelcode/PulseDB#key-design-decisions)

---

### 🌱 GreenScore &nbsp;·&nbsp; Full-stack sustainability platform
> *Security was a design requirement from the first commit, not a later patch.*

A PHP and MySQL web application where organisations score their environmental impact across 10 categories, earn badge levels, and receive downloadable certificates. It has a role-based admin dashboard, a community board, and a feedback system.

- **42 PHPUnit tests** covering authentication, scoring thresholds, input validation and ownership checks
- Prepared statements, CSRF tokens, `password_hash()`, session regeneration, login rate limiting and hardened cookies
- Built as a Graded Unit 2 assessment at Edinburgh College, then taken further for security and testing

`PHP 8.2` `MySQL` `Bootstrap 5` `PHPUnit` `Security` `Session Management`

[Repository](https://github.com/Lancelcode/GreenScore)

---

## `$ ls projects/other/`

| Project | What it is | Stack |
|---|---|---|
| 🔍 [nvvri](https://nvvri.vercel.app) | AI-assisted nursery finder with natural-language search across area, age range, Ofsted rating and price | TypeScript, Next.js 15, React 19 |
| 🔧 project-manager-api | REST API with JWT authentication, role-based access control, PostgreSQL, Docker and a GitHub Actions pipeline | Java 21, Spring Boot, PostgreSQL |
| 🎓 [Revision kit](https://github.com/Lancelcode/adb-revision-lab) | Docker-based labs, question bank and quiz for advanced database systems | PostgreSQL, MongoDB, Python |

---

## `$ cat rebuilding-the-stack.md`

Systems I am rebuilding from protocol level, because *if you can build it, you understand it*:

| Tool | Status | What it taught me |
|------|--------|-------------------|
| PulseDB (Redis-compatible server) | ✅ Complete | Event loops, RESP parsing, data structures, sanitizers |
| Group chat (sockets) | ✅ Complete | TCP, multi-client handling, concurrency |
| Own shell | 🔄 In progress | Process forking, pipes, signals, PATH resolution |
| AI coding agent | 🔄 In progress | LLM APIs, tool calling, agent loops |
| Git internals | 📋 Planned | Content-addressable storage, DAGs, hashing |
| Compiler (subset) | 📋 Planned | Lexing, parsing, AST, code generation |

---

## `$ ls security/`

Hands-on security learning: penetration testing, log analysis, CVE research and hardening, through TryHackMe and Hack The Box tracks. *Offensive skills make better defensive engineers.*

`Parrot OS` `Linux` `Pen Testing` `CVE Analysis` `Hardening`

---

## `$ cat stack.txt`

**Languages**

![Mojo](https://img.shields.io/badge/Mojo-FF4C1F?style=for-the-badge&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?style=for-the-badge&logo=php&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Frameworks & frontend**

![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)

**Data & testing**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![PHPUnit](https://img.shields.io/badge/PHPUnit-6C9FCC?style=for-the-badge&logo=php&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit-25A162?style=for-the-badge&logo=junit5&logoColor=white)

**Infrastructure & tools**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=github-actions&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)

**Security**

![Parrot OS](https://img.shields.io/badge/Parrot_OS-1de3c1?style=for-the-badge&logo=linux&logoColor=black)
![OWASP](https://img.shields.io/badge/OWASP-000000?style=for-the-badge&logo=owasp&logoColor=white)

---

## `$ cat current_learning.log`

```
[2026] █████████░░░░░░░░░░░  Python at depth          — OOP, testing, packaging
[2026] ██████░░░░░░░░░░░░░░  Mojo & SIMD              — vectorisation, parallel kernels
[2026] ██████░░░░░░░░░░░░░░  AI/ML foundations        — numpy, pandas, scikit-learn
[2026] ████████░░░░░░░░░░░░  Applied security         — TryHackMe, PortSwigger
[2026] ████████████░░░░░░░░  Systems programming      — memory, concurrency, I/O
```

The roadmap: strong systems foundations → performance engineering → ML engineering → DevSecOps.
Security makes me a better engineer. Systems knowledge makes me a better security researcher. ML gives me new tools for both.

---

## `$ cat philosophy.txt`

I came into software engineering from an unusual direction: figuring things out because I had to, not from a computer science family or a bootcamp. That made me comfortable not knowing something, because not knowing has always been the starting point.

I build things from scratch not to reinvent wheels, but because you cannot truly understand a wheel until you have tried to build one.

Long term: DevSecOps and AI-driven security tooling. Right now: the foundations that make those goals realistic.

> If not me, who? If not now, when?

---

## `$ echo "Let's talk"`

Working on backend systems, performance, security tooling or infrastructure? I'd like to hear about it.

[![LinkedIn](https://img.shields.io/badge/Reach_out_on_LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/djiby-sow-rebollo/)

<div align="center">
<sub>⚡ Actively building · 📍 Edinburgh, Scotland · 🎯 Open to junior engineering roles from late 2026</sub>
</div>

---

<div align="center">

![GitHub stats](./profile/stats.svg)
![Top Languages](./profile/top-langs.svg)

</div>
