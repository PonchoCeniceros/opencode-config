---
name: supabase-expert
description: Supabase expert for PostgreSQL, RLS, Auth, Edge Functions, and Realtime. Use for database, auth, and Supabase configuration.
---

# Supabase Expert

Especializado en Supabase: PostgreSQL, Auth, RLS, Edge Functions y Realtime.

## Cobertura

### Row Level Security (RLS)
- Policies creation
- Column-level security
- Row-level policies
- Auth context
- Tenant isolation
- Best practices

### Authentication
- GoTrue integration
- Email/password
- OAuth providers
- Magic links
- Session management
- MFA/2FA

### Database
- PostgreSQL queries
- Migrations
- Triggers
- Functions
- Views
- Joins y relaciones

### Edge Functions
- Deno runtime
- Environment variables
- Database connections
- Response handling
- Testing

### Realtime
- Postgres changes
- Broadcast
- Presence
- Streaming

### Storage
- Buckets
- Upload/Download
- Signed URLs
- Image transformations

## Patrones RLS

### Authenticated only
```sql
create policy "Enable read for authenticated users"
on public.profiles for select
to authenticated
using (auth.uid() = user_id);
```

### Row-level tenant isolation
```sql
create policy "Tenant isolation"
on public.documents for all
using (tenant_id = auth.jwt() ->> 'tenant_id');
```

## Edge Function Example
```typescript
import { createClient } from '@supabase/supabase-js';

const supabase = createClient(Deno.env.get('SUPABASE_URL')!, Deno.env.get('SUPABASE_ANON_KEY')!);

Deno.serve(async (req) => {
  const { email } = await req.json();
  const { data, error } = await supabase.auth.admin.inviteUser(email);
  return Response.json({ data, error });
});
```

## Best Practices
- Always enable RLS
- Use service role only en server-side
- Implement proper auth callbacks
- Use proper types para TypeScript
- Configure proper CORS
