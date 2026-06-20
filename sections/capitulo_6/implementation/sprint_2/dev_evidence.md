En la siguiente tabla se muestran los commits realizados en la organización Soulware-IoT en el sprint 2.

| Repositorio | Branch | Commit Id | Commit Message | Commit Message Body | Commitido en (Fecha) |
|-------------|--------|-----------|----------------|---------------------|----------------------|
| api-gw | develop | 4d1c21d | chore: updated dependencies and tsconfig | | 2026-05-28 |
| api-gw | develop | 1fe7bc8 | refactor: turn 'SupabaseAuthGuard' into 'AuthenticationGuard' | | 2026-05-28 |
| api-gw | develop | 9e560e0 | feat: stablish guards for the bounded context | | 2026-06-12 |
| api-gw | develop | c3974e8 | feat: add controllers and service for bounded contexts | | 2026-06-18 |
| api-gw | feature/debug | b06fb91 | feat: add security endpoints | | 2026-06-19 |
| api-gw | feature/debug | 14076bd | fix(api-gw): wire modules, fix permission guards, relay backend errors | | 2026-06-19 |
| api-gw | feature/api-gw-routing-refactor | 745763b | refactor(api-gw): per-context route constants, headers class, single BACKEND_URL | | 2026-06-19 |
| api-gw | feature/i18n-errors-and-org-list | 18b75cf | feat(api-gw): localize gateway errors via Accept-Language + expose GET /organizations | | 2026-06-20 |
| api-gw | main | 4caccaa | fix(api-gw): align Security device routes with backend main | | 2026-06-20 |
| api-gw | main | 96a1b3c | feat(api-gw): enable CORS for web clients + widen BoundedContext type | | 2026-06-20 |
| backend | feature/profiles | 5a09a2a | feat: add profiles context | | 2026-06-17 |
| backend | feature/profiles | 88dd614 | feat: add global exception handler for prettier exception responses | | 2026-06-17 |
| backend | feature/profiles | 865b51f | feat: add exception response i18n | | 2026-06-17 |
| backend | feature/organizations | 5e6defe | fix: amend database compatibility | | 2026-06-18 |
| backend | feature/organizations | 797194f | feat: add i18n for domain exceptions on organizations service | | 2026-06-18 |
| backend | feature/organizations | 46516d5 | refactor: split application and interface layers by resource | | 2026-06-18 |
| backend | feature/organizations | 3ea3d12 | fix: resolve profile details instead of returning profileId | | 2026-06-18 |
| backend | feature/internal-control | adb11a9 | feat: add INTEGER vs DECIMAL number kind to domain model | | 2026-06-18 |
| backend | feature/internal-control | 97731f9 | feat: add basic control format endpoints | | 2026-06-18 |
| backend | feature/internal-control | 6e66b37 | feat: add control processes controller | | 2026-06-18 |
| backend | feature/security | 190d3b8 | feat: add basic device registration endpoints | | 2026-06-18 |
| backend | feature/security | 926a14f | feat: add get invitations by userId | | 2026-06-19 |
| backend | feature/security | 6e1cd0b | feat: add audit for device registration | | 2026-06-19 |
| backend | feature/security | bef2947 | feat: add device registration flow endpoints | | 2026-06-19 |
| backend | feature/security | 464b3ef | fix: add missing validations for endpoints | | 2026-06-19 |
| backend | feature/security | 86051d8 | refactor: rework the registration and authentication flow for edge and iot devices | | 2026-06-19 |
| backend | feature/security | 0be6059 | feat: add update thresholds endpoint | | 2026-06-19 |
| backend | feature/security | 4467102 | feat: add device fetch endpoint | | 2026-06-19 |
| backend | feature/security | 8b2c7fd | feat: add iot management endpoints | | 2026-06-19 |
| backend | feature/security | 2feea98 | feat: add edge device management endpoints | | 2026-06-19 |
| backend | feature/security | 3e39b07 | feat: add get organizations by userId | | 2026-06-19 |
| backend | feature/security | f8ecd18 | refactor: merge endpoints | | 2026-06-19 |
| backend | feature/security | c548b53 | fix: amend endpoint resource names for better consistency | | 2026-06-19 |
| backend | feature/security | d71c923 | feat: add cors config | | 2026-06-19 |
| backend | feature/security | 2805748 | refactor: nest jpa entity-specific classes inside jpa package | | 2026-06-19 |
| backend | develop | df3a3a6 | feat: add telemetry using mongodb | | 2026-06-20 |
| backend | develop | 755278a | fix: amend PermissionLevel enum | | 2026-06-20 |
| mobile-app | feature/auth | fc13a21 | refactor: upgrade visual for login page | | 2026-06-10 |
| mobile-app | feature/auth | 0e8551c | refactor: upgrade register page | | 2026-06-10 |
| mobile-app | feature/auth | e38cf7b | feat: add application router | | 2026-06-10 |
| mobile-app | feature/auth | c560080 | tests: AuthRepositoryImpl y ProfileRepositoryImpl | | 2026-06-10 |
| mobile-app | develop | a4eed83 | feat: rebrand a Cocina360 (icono, splash, nombre y tema) | | 2026-06-17 |
| mobile-app | develop | a78b6ee | feat(auth): add logout action to home AppBar | | 2026-06-18 |
| mobile-app | feature/organization-screen | eadbec9 | feat(organization): add Organization screen consuming the api-gw | | 2026-06-18 |
| mobile-app | feature/organization-api-integration | 7d4dc89 | fix(organization): wire Organization screen to the real api-gw + emulator networking | | 2026-06-19 |
| mobile-app | feature/edit-organization | 1abb62a | feat(organization): edit organization screen | | 2026-06-19 |
| mobile-app | feature/member-management | 5e76299 | feat(organization): member detail, edit permissions, invite members | | 2026-06-19 |
| mobile-app | feature/member-management | ac681ca | feat(member-management): include invitations module | | 2026-06-19 |
| mobile-app | feature/i18n-and-org-switcher | a17095e | feat(i18n+org): localized error messages (ES/EN) and organization switcher in drawer | | 2026-06-20 |
| mobile-app | develop | 61380a5 | fix(invitations): refresh session + organizations list after accepting | | 2026-06-20 |
| mobile-app | feature/devices-read | 8d77489 | feat(devices): read-only Devices screen (list + detail) via api-gw GET endpoints | | 2026-06-20 |
| mobile-app | develop | d0b8457 | feat: rename iot to organization | | 2026-06-20 |
| mobile-app | develop | 62fdfc4 | fix: amend bad dto mapping | | 2026-06-20 |
| mobile-app | develop | c6e8ae5 | fix: amend i18n | | 2026-06-20 |
| edge-application | main | 85e5c4a | feat: add edge device authentication via edge gateway | | 2026-06-19 |
| edge-application | develop | d5755ab | feat: add insta app crash if configuration is not successful | | 2026-06-19 |
| edge-application | develop | 3d63298 | feat: add device polling | | 2026-06-19 |
| edge-application | develop | f9e9450 | feat: add readings context | | 2026-06-20 |
| edge-gw | main | 0069ac7 | feat: add edge device authentication request forwarding | | 2026-06-19 |
