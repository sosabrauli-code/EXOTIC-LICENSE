# EXOTIC LICENSE
1. Supabase > SQL Editor: ejecuta `scripts/001_exotic_license_schema.sql`.
2. Supabase > Authentication > Users: crea tu usuario administrador.
3. En SQL Editor ejecuta `scripts/002_register_admin.sql` después de reemplazar el correo.
4. Copia `.env.example` a `.env.local` y completa URL, anon key y service role key.
5. En Vercel > Project Settings > Environment Variables agrega las mismas variables. La service role key debe quedarse solo del lado servidor; nunca uses NEXT_PUBLIC_ en ella.
6. Sube el proyecto a GitHub y en Vercel importa el repositorio como Next.js.
API MTA: POST `/api/verify` con JSON `{"key":"EXO-...","resource":"nombre_recurso"}`. La respuesta `valid:false` significa que debe bloquearse el recurso.
Este proyecto requiere configurar Supabase antes de funcionar. Cada recurso MTA debe incluir su propio código Lua para consultar periódicamente la API; la web no puede detener un recurso si este no realiza la comprobación.
