# WE Team Performance - Firebase + Google Sheets Schema

## Collections

### `leads`
- name
- sex
- age
- occupation
- tel
- line
- social
- interests: array
- approaches: array
- sponsorId
- ownerUid
- ownerEmail
- googleName
- createdAt
- updatedAt

### `brandAffiliates`
- name
- nuskinId
- tel
- line
- social
- status
- productStart
- gsvGoal
- gsvActual
- sponsorId
- ownerUid
- ownerEmail
- googleName
- createdAt
- updatedAt

## Team Tree Logic

Team Tree does not need a separate collection. It is calculated from the `brandAffiliates` collection.

Rule:

```text
Downline.sponsorId = Upline.nuskinId
```

Example:

```text
Ong Leader: nuskinId = TH0001, sponsorId = blank
Level 1 BA: nuskinId = TH0002, sponsorId = TH0001
Level 2 BA: nuskinId = TH0003, sponsorId = TH0002
```

The app calculates:

- Level number
- Personal GSV
- Team GSV, including the BA and all downlines
- Number of downlines
- Root leaders
- Search by upline NuSkin ID or name

## Google Sheets tabs

### Leads
Record ID, Created At, Updated At, Deleted At, Name, Sex, Age, Occupation, Tel, Line ID, FB / IG, Interest, Approach, Sponsor ID, Owner UID, Owner Email, Google Name

### Brand Affiliates
Record ID, Created At, Updated At, Deleted At, Name, NuSkin ID, Tel, Line ID, FB / IG, Status, Product Start, GSV Goal, GSV Actual, Sponsor ID, Owner UID, Owner Email, Google Name

## Status values

BA, LOI, BR, Gold, Lapis, Ruby, Emerald, Diamond, Blue Diamond, Team Elite
