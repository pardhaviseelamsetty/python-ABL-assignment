# python-ABL-assignment
1to10 tasks 
 Problem Statement
Shortlist applicants using marks, attendance, family income, ranking score, and a fixed quota.

2. Pseudocode
INPUT quota and applicants
FOR each applicant: check marks >= 60, attendance >= 75, income <= 250000
Record failed conditions; otherwise add to eligible list
Sort eligible by score descending; select first quota
DISPLAY selected, eligible-not-selected, rejected

3. Source Code (Python)
quota=int(input("Quota: "))
n=int(input("Applicants: "))
eligible=[]; rejected=[]
for _ in range(n):
name=input("Name: "); marks=float(input("Marks %: "))
att=float(input("Attendance %: ")); income=float(input("Annual income: "))
score=float(input("Ranking score: "))
reasons=[]
if marks<60: reasons.append("marks below 60%")
if att<75: reasons.append("attendance below 75%")
if income>250000: reasons.append("income above limit")
if reasons: rejected.append((name,", ".join(reasons)))
else: eligible.append((score,name))
eligible.sort(reverse=True)
print("Selected:",eligible[:quota])
print("Eligible but outside quota:",eligible[quota:])
print("Rejected:",rejected)

5.```Mermaid Flowchart
#flowchart TD
A([Start])-->B[/Input quota and applicants/]
B-->C[Check each applicant]
C-->D{All conditions met?}
D--Yes-->E[Add to eligible list]
D--No-->F[Record rejection reasons]
E-->G{More applicants?}
F-->G
G--Yes-->C
G--No-->H[Sort by score and apply quota]
H-->I[/Display report/]
I-->J([End])```

6. Input
Quota; applicant name, marks, attendance, annual income, ranking score.

8. Output
Selected applicants, eligible applicants outside quota, and rejected applicants with reasons
