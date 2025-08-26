erDiagram
  Reservation ||--o{ Transfer : has
  Transfer ||--o{ SupplierAssignment : assigned_to
  SupplierAssignment }o--|| Supplier : of
  Transfer }o--|| AreaOfOps : in
  AreaOfOps }o--|| User : bd_agent

  SupplierAssignment ||--o{ ReconfirmationLine : tracked_by
  ReconfirmationLine ||--o{ ReconfCommunication : logs
  ReconfirmationLine }o--|| User : managed_by

  ReconfConfig ||--o{ AreaOfOps : applies_to
  ReconfConfig ||--o{ Supplier : overrides_for
