# Grupp 6 — Learning Management System (LMS)

Ett **Learning Management System** byggt som en distribuerad lösning med microservices. Kursprojekt i *Molntjänster och distribuerade system* på EC Utbildning.

> Frontend: **Next.js** · Backend: **ASP.NET Core Web API** · Moln: **Azure + Vercel** · Planering: **Jira (Kanban)**

## Om projektet

Vi bygger ett LMS. Kurser, anmälningar, uppgifter, betyg, notiser med mera, uppdelat i flera självständiga tjänster. **Varje tjänst har ett eget repo** i den här organisationen. Frontend ligger i ett gemensamt repo som hela gruppen jobbar i.

## Stack

| Del | Val |
|---|---|
| Frontend | Next.js (App Router) + TypeScript + Tailwind + shadcn/ui - deployas på Vercel |
| Backend | ASP.NET Core Web API (.NET) - en tjänst per repo, deployas på Azure |
| Databas | Azure SQL - en databas per utvecklare, ett schema per tjänst, inga kopplingar mellan olika tjänsters tabeller |
| Kommunikation mellan tjänster | REST · gRPC · Azure Service Bus · SignalR - väljs efter behov |
| API-dokumentation | Scalar |
| Auth | JWT (access- + refresh-tokens), rollbaserad åtkomst |
| Planering | Jira (Kanban) |

## Repos

- **`lms-frontend`** - Next.js-frontend, hela gruppen jobbar här
- **Tjänster** (egna repos, skapas allt eftersom) - t.ex. `auth-api` (inloggning/JWT), `course-api` (kurskatalog), `usercourses-api` (anmälningar), `assignments-api`, `grading-api`, `reviews-api`, `schedule-api`, `discussion-api`, `profile-api`, `notifications-api`, `email-service`, `media-storage-api`, `user-api`, m.fl.
- **`.github`** - det här repot (org-profil + ev. gemensamma mallar)

## Arbetssätt

- En tjänst = ett repo. Branch → Pull Request → review innan merge till `main`.
- Jira-nyckeln (`KAN-xx`) med i branchnamn och commits.
- **Inga secrets i Git** - `.env` lokalt, GitHub Secrets / Azure-konfiguration i molnet. (Repos är publika.)
- Gemensam README-mall, mappstruktur och commit-konventioner mellan alla repos.
