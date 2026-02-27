# Admin Use Case Diagram (UML Style)

This version is in the same formal style as your sample: one actor, system boundary, use-case ovals, and correct `<<include>>` / `<<extend>>` relations.

```plantuml
@startuml
left to right direction
skinparam packageStyle rectangle

actor Admin

rectangle "AI-Enhanced Quiz Management System" {

    usecase "Login / Authenticate" as UC_Login
    usecase "Two-Factor Authentication" as UC_2FA
    usecase "Reset Password" as UC_Reset
    usecase "Manage Profile" as UC_Profile

    usecase "Manage User Accounts" as UC_UserAccounts
    usecase "Create User Account" as UC_CreateUser
    usecase "Update User Account" as UC_UpdateUser
    usecase "Deactivate User Account" as UC_DeactivateUser

    usecase "Manage Courses / Categories" as UC_CourseMgmt
    usecase "Create Course / Category" as UC_CreateCourse
    usecase "Update Course / Category" as UC_UpdateCourse
    usecase "Archive Course / Category" as UC_ArchiveCourse

    usecase "Monitor System Security" as UC_Security
    usecase "View Audit Logs" as UC_Audit
    usecase "Track Login Attempts & IP Events" as UC_TrackEvents

    usecase "Generate Global Analytics" as UC_Analytics
    usecase "View System Usage Trends" as UC_UsageTrends
    usecase "View Institution Pass/Fail Rates" as UC_PassFail
}

' Actor associations (plain association links)
Admin -- UC_Login
Admin -- UC_Profile
Admin -- UC_UserAccounts
Admin -- UC_CourseMgmt
Admin -- UC_Security
Admin -- UC_Analytics

' Extend relationships (optional / conditional)
UC_2FA ..> UC_Login : <<extend>>
UC_Reset ..> UC_Login : <<extend>>

' Include relationships (mandatory decomposed behavior)
UC_UserAccounts ..> UC_CreateUser : <<include>>
UC_UserAccounts ..> UC_UpdateUser : <<include>>
UC_UserAccounts ..> UC_DeactivateUser : <<include>>

UC_CourseMgmt ..> UC_CreateCourse : <<include>>
UC_CourseMgmt ..> UC_UpdateCourse : <<include>>
UC_CourseMgmt ..> UC_ArchiveCourse : <<include>>

UC_Security ..> UC_Audit : <<include>>
UC_Security ..> UC_TrackEvents : <<include>>

UC_Analytics ..> UC_UsageTrends : <<include>>
UC_Analytics ..> UC_PassFail : <<include>>

@enduml
```

## Quick reading guide

- `Admin -- Use Case`: Admin participates in that functionality.
- `<<include>>`: mandatory sub-function inside the parent use case.
- `<<extend>>`: optional/conditional behavior added to a base use case.

## Why this is complete for Admin scope

- Covers all common Admin-access functions (login/profile).
- Covers governance tasks (users, courses/categories).
- Covers security oversight (audit logs and event tracking).
- Covers institutional reporting (global analytics, trends, pass/fail).