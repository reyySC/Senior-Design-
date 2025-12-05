# User Stories — TA Scheduling Optimization Tool


## Background / Scope
This tool automates assigning TAs to course sections given applicant preferences, skills, and availability. It follows the constraints and workflow discussed in the kickoff meeting, including availability parsing, constraint-based optimization using CP-SAT, skill balancing, and exclusion flags.

## User Stories

1. **TA coordinator** : In order for the tool to automatically parse and ingest the applicant data for scheduling, as a TA coordinator, I would want to input applicant data (application form + availability).
   - *Goal:* Reduce manual data entry and mistakes.
   Benefits include time savings for coordinators and increased availability data dependability.

2. **TA Applicant** : As a TA candidate, I would like my availability to be parsed from a PDF schedule or a form so that my actual free time is recorded without the need for manual re-entry.
   The objective is to make sure that scheduling takes into account real course conflicts.
   Benefits include fewer assignment disputes and reduced rework for coordinators and TAs.

3. **TA coordinator**: In order to ensure that assignments meet departmental requirements (skill balance, variety, preferences) and availability, I want the application to create several workable schedules and choose the optimal one based on weighted rules (hard constraints > soft preferences).
   The objective is to create an optimal timetable that respects restrictions.
   Benefits include less manual adjustment and better-balanced parts.

4. **Administrator** : In order to ensure that the generated schedules only include qualified candidates, I would want to automatically eliminate ineligible applications (inclusion flag = 0).
   The objective is to automate exclusion logic in advance.
   * Advantage:* Prevents human mistake and expedites the selection of candidates.

5. **Course instructor**:  To guarantee that every part has the necessary skill coverage, I want each section to have a 3-TA team with at least one TA who is proficient in Python, one in CAD, and one in Excel.
   * Objective:* Fulfill the department's skill standards for each section.
   * Advantage:* Better lab assistance for students.

6. **TA coordinator** : In order to minimize interpersonal disputes, I would need the tool to not assign a TA to a professor or section if they had a bad experience.
   * Objective:* Honor exclusions stated by applicants.
   Benefits include safer and more cooperative teams.

7. **TA coordinator** : I want an easy-to-use GUI (or single-command script) that allows non-programmers to use the tool and export the final schedule as PDF and Excel.
   The objective is to enable administrators without any coding experience to use the tool.
   Benefits include increased uptake and quicker deployment.



## Acceptance Criteria
- Uploads parse both CSV (form) and PDF schedules reliably.
- Inclusion flag (0/1) respected — 0 means excluded prior to generation.
- Hard constraints (availability, 10-minute gap from own classes, no assigned conflicts) are never violated.
- Each section (3 TAs) contains at least one Python, one CAD, one Excel proficient TA.
- The default output is an Excel file (assignments) and a PDF summary.
- The tool supports manual post-generation overrides.


