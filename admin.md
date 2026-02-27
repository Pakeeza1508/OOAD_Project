@startuml
title Admin Use Case Diagram - AI-Enhanced Quiz Management System
left to right direction
skinparam packageStyle rectangle

'========================
' Actors
'========================
actor "Primary User" as PrimaryUser
actor "Admin" as Admin

' Generalization (Admin inherits common behavior of Primary User)
PrimaryUser <|-- Admin

'========================
' System Boundary
'========================
rectangle "AI-Enhanced Quiz Management System" {

	' Common Use Cases
	usecase "Login / Authenticate" as UC_Login
	usecase "Two-Factor Authentication" as UC_2FA
	usecase "Reset Password" as UC_ResetPwd
	usecase "Manage Profile" as UC_Profile

	' Admin Use Cases
	usecase "Manage User Accounts" as UC_UserAccounts
	usecase "Manage Courses / Categories" as UC_Courses
	usecase "Monitor System Security" as UC_Security
	usecase "View Audit Logs" as UC_AuditLogs
	usecase "Generate Global Analytics" as UC_GlobalAnalytics
}

'========================
' Actor Associations
'========================
Admin --> UC_Login
Admin --> UC_Profile
Admin --> UC_UserAccounts
Admin --> UC_Courses
Admin --> UC_Security
Admin --> UC_GlobalAnalytics

'========================
' UML Relationships
'========================
UC_2FA ..> UC_Login : <<extend>>
UC_ResetPwd ..> UC_Login : <<extend>>
UC_Security ..> UC_AuditLogs : <<include>>

' Optional note to explain included behavior
note right of UC_AuditLogs
Tracks login attempts,
IP addresses, and security events.
end note

@enduml