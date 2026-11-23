# Product Requirements Document (PRD)
## Hostel Maintenance Complaint Tracker for Babcock University

Course: BU-209 Backend Engineering, Week 4 Assignment
Team: Byte Syndicate
Members:
- Akorede Praise (Team Leader)
- Adeyinka Adedotun
- Adeola Akitoye
- Adeniyi Isaac
- Adebowale Isaac

Date: 23/11/2026

---

## 1. Introduction

This document is about a problem we noticed in the halls of residence at Babcock University, what we found out about it, and the first version of a system that could help. We have not picked a programming language yet. We wanted to understand the problem properly first.

## 2. The Problem

Things break in the halls all the time: taps, door locks, sockets, lights. When that happens, the student has to report it to the porter. In most cases the porter tells you to write it in a complaint book kept at the porter's desk, and after that you hear nothing.

This happened to me in Winslow Hall. My door broke and my tap stopped working. I told the porter and he said I should write it in the book. It took almost 2 to 3 weeks before a technician came to fix both. Within that time I went back to ask a few times, and the answer was always something like the technician is not around, or he will get to your room soon.

The slow repair is not the only issue. Nobody can see what is happening with a complaint. The student does not know if it was read, the technician does not have a proper list of what to fix, and the hall officers cannot tell which faults keep repeating. A book at a desk cannot show any of that.

## 3. Who Has This Problem

- Students in the halls: they report a fault and then wait with no feedback.
- Porters: they receive the complaints and get asked for updates, but they have nothing to check.
- Technicians: they do not have a clear list of jobs.
- Hall officers: they cannot see patterns or how long repairs take.

## 4. How People Handle It Today

From my own experience and our survey, students either tell the porter, write in the complaint book, go to the hall office, or keep going back to ask. None of these gives the student a receipt or a way to check progress.

## 5. Why the Current Method Falls Short

The complaint book is the only system we found, and it has these problems:

1. There is no confirmation that the complaint was received.
2. There is no status, so the student can only keep asking people.
3. A book is hard to search and entries can easily be missed.
4. It cannot give management any summary, for example how many tap complaints came from one hall in a month.

## 6. Research Method

We surveyed 7 students through WhatsApp. They live in Winslow Hall, Samuel Akande Hall and Neal Wilson Hall. We asked what fault they had, how they reported it, how long it took to be fixed, whether they were told the status, how satisfied they were (1 to 5), and whether they would use a website to report and track complaints. I also used my own experience in Winslow as a case.

## 7. Survey Findings

| Question | Result |
|---|---|
| Fault took more than a week or was never fixed | 5 of 7 (71.4%) |
| Got updates on their complaint | 2 of 7 (28.6%) |
| Repair done within 1 to 3 days | 2 of 7 (28.6%) |
| Average satisfaction | 2.3 out of 5 |
| Would use a website to report and track complaints | 5 yes (71.4%), 1 unsure (14.3%), 1 no (14.3%) |

Most students waited more than a week or never got their fault fixed, and only 2 of the 7 were told anything about their complaint. Two students had their repairs done in 1 to 3 days, so quick repairs do happen, it is just not consistent. Most of the students said they would use a website for this.

The main problems we found are delayed repairs, poor communication and no way to track a complaint. A central website where students submit complaints, see progress and get updates would deal with the last two directly.

## 8. Proposed Solution

A web-based maintenance complaint tracker. The student logs in, submits the fault and gets a reference number. The complaint then moves through clear statuses that the student can check any time. Hall officers assign complaints to technicians, and technicians update the status as they work.

## 9. Users and Roles

| Role | Can do | Needs to see |
|---|---|---|
| Student | Submit a complaint, track its status | Their own complaints and status |
| Porter | Log a complaint for a student at the desk, update status | Complaints for their hall |
| Technician | Accept a job, mark it in progress or fixed | Their assigned jobs |
| Hall officer | Assign jobs, view all complaints | All complaints with fault type and age |

## 10. MVP (Version 1)

The first version only needs to fix the main problem, which is that students get no confirmation and no status.

Included:

1. Student login (matric number and password)
2. Submit a complaint with hall, room number, fault type and description
3. Every complaint gets a reference number and a status: Received, Assigned, In Progress, Fixed
4. Student can view their own complaints and statuses
5. Hall officer can view all complaints and assign them to a technician
6. Technician can update the status of their assigned jobs

Left out for later: photo uploads, SMS or email notifications, analytics dashboard, priority levels and automatic reminders. We left these out so the first version stays small enough to finish and test.

## 11. Backend Considerations

We have not chosen a language or framework. Whatever we use, the backend has to handle the following:

- Data to store: users (with roles), complaints, halls, and a history of status changes.
- Relationships: each complaint belongs to one student and one hall, and can be assigned to one technician.
- Access rules: a student should only see their own complaints, only hall officers can assign jobs, and only the assigned technician can update a job's status.
- History: every status change should be saved with who made it and when, so management can later see how long repairs really take.
- Authentication: users must log in so the system knows who is who, and passwords must be stored hashed, never as plain text.

## 12. Success Metrics

We will know the system is helping if:

- more complaints get a status update (right now it is 2 of 7 in our survey),
- the average time from complaint to fix goes down,
- satisfaction goes above the 2.3 out of 5 we got,
- porters and technicians actually use it and not just students.

## 13. Conclusion

The current complaint process in the halls is slow and students cannot see what is happening with their complaints. A simple tracker that gives a reference number and a visible status is a practical first step, and it is something we can build as a small backend project.
