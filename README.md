# Network+ Journey

A practical, beginner-friendly record of my journey toward CompTIA Network+. This repository pairs a structured study plan with hands-on labs, troubleshooting notes, and progress reviews so other learners can adapt it to their own course and home lab.

## Start here

1. Confirm which Network+ exam version your course or instructor expects.
2. Download the matching exam objectives from CompTIA and use them as the checklist for your preparation.
3. Follow the [eight-week study plan](docs/study-plan.md) at a pace that fits your schedule.
4. Record weekly wins and weak areas with the [progress log](templates/weekly-progress.md).
5. Practice only on systems and networks you own or have permission to use. The [lab safety notes](docs/lab-safety.md) explain the examples here.

## What is here

- [Study plan](docs/study-plan.md): a repeatable weekly routine and exam-domain roadmap.
- [Progress log template](templates/weekly-progress.md): track study, practice, and next steps.
- [Subnetting practice](labs/subnetting-practice.md): a worked approach and exercises.
- [Network troubleshooting lab](labs/troubleshooting-basics.md): a safe, evidence-based workflow.
- [Isolated Proxmox lab blueprint](labs/isolated-proxmox-network-lab.md): a small two-guest lab for DNS, HTTP, packet capture, and troubleshooting.
- [Lab safety](docs/lab-safety.md): scope, isolation, and cleanup.

## Resources

- [Professor Messer’s free N10-009 video course](https://www.professormesser.com/network-plus/n10-009/n10-009-video/n10-009-training-course/)
- [Professor Messer’s N10-009 study group replays](https://www.professormesser.com/network-plus/n10-009/n10-009-study-group/n10-009-network-study-group-replay/)
- [Professor Messer’s Network+ study resources](https://www.professormesser.com/netplus-resources/)
- [CompTIA Network+ certification](https://www.comptia.org/certifications/network)

Professor Messer’s lessons and materials belong to Professor Messer. This project links to his resources and does not copy or redistribute his videos, notes, or practice questions. Check the official CompTIA objectives and your instructor’s direction for the exam version you will take.

## Course context

I am using this project alongside DSDT College’s Technology Professional 6 certificate. The published program description lists three 80-hour courses—CTN-102 CompTIA Network+, SYO-701 CompTIA Security+, and CS0-002 CompTIA CySA+—for 240 clock hours over three months, with 50 theory and 30 lab hours per course. DSDT describes instructor-led lectures, discussion, interactive applications, and virtual lab sessions; it also lists Hack The Box Labs among the software. Attendance is mandatory. The school page says syllabi may change, so the instructor’s current syllabus, exam objectives, and assignments take priority.

My immediate milestone is Network+. I use the [eight-week study plan](docs/study-plan.md) as supplemental structure around class, not as a replacement for the class schedule. Professor Messer’s linked lessons cover N10-009; DSDT’s page does not name the Network+ exam version, so confirm alignment with the instructor before treating N10-009 as the required version or booking an exam. The [DSDT program description](https://dsdt.edu/programs/technology-professional-6-program/) is the source for program details.

## How I practice

Learn the course concept, recall it without notes, apply it in an instructor-approved virtual lab or isolated home lab, then write a short evidence-based report. My initial home-lab pattern is a toolbox guest and a target guest on an isolated virtual network. Practice is limited to systems I own or have explicit permission to use. A safe learning sequence is addressing and routes, DNS/HTTP behavior, packet capture, basic service checks against the lab target, then a controlled break/fix and verification. Explain observations and uncertainty; do not treat a scan result as proof of compromise.

This is a living study journal. I’ll add dated progress updates, lessons learned, and lab write-ups as I work through the material. Personal details, account information, private addresses, host access links, and private lab configuration do not belong in this repository.

## Progress

See the [dated progress log](progress/2026-10-03.md) for the current course setup and next actions.

## License

The original notes and templates in this repository are shared under the [Creative Commons Attribution 4.0 International license](LICENSE). External resources retain their own licenses and ownership.
