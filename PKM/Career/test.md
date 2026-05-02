export http_proxy="http://10.190.204.61:8964"
export https_proxy="http://10.190.204.61:8964"
export ftp_proxy="http://10.190.204.61:8964"

```
Acadex/                        ← Root workspace
├── apps/
│   ├── api/                       ← NestJS backend (Node.js)
│   │   ├── src/
│   │   │   ├── modules/
│   │   │   │   ├── auth/
│   │   │   │   ├── users/
│   │   │   │   ├── courses/
│   │   │   │   ├── enrollment/
│   │   │   │   ├── attendance/
│   │   │   │   └── grades/
│   │   │   ├── common/            ← Guards, interceptors, pipes
│   │   │   ├── config/            ← ConfigModule, env validation
│   │   │   ├── database/          ← TypeORM setup, migrations
│   │   │   └── main.ts
│   │   ├── test/
│   │   └── Dockerfile
│   │
│   ├── web-admin/                 ← Next.js 14 (Admin + Teacher)
│   │   ├── app/                   ← App Router
│   │   │   ├── (auth)/
│   │   │   ├── dashboard/
│   │   │   ├── courses/
│   │   │   ├── users/
│   │   │   ├── attendance/
│   │   │   └── grades/
│   │   └── Dockerfile
│   │
│   └── web-student/               ← Next.js 14 (Student portal)
│       ├── app/
│       │   ├── (auth)/
│       │   ├── my-courses/
│       │   ├── attendance/
│       │   └── grades/
│       └── Dockerfile
│
├── packages/
│   ├── ui/                        ← Shared React component library
│   │   ├── src/components/
│   │   └── src/styles/
│   ├── types/                     ← Shared TypeScript types & DTOs
│   ├── config/                    ← ESLint, Prettier, TSConfig base
│   ├── validators/                ← Shared Zod / class-validator schemas
│   └── utils/                     ← Date helpers, formatting, constants
│
│
├── turbo.json                     ← Turborepo pipeline config
├── pnpm-workspace.yaml
└── package.json
```