# Configuración de OpenCode

Configuración personal para el asistente de IA OpenCode.

## Instalación

Copia el contenido de este repositorio a `~/.config/opencode/`:

```bash
cp -r * ~/.config/opencode/
```

O crea un enlace simbólico:

```bash
ln -s /path/to/opencode-config ~/.config/opencode
```

## Contenido

### Configuración
- `config.json` - Configuración principal con tema, MCPs y permisos

### Agentes
- `mobile-dev` - Experto en React Native/Expo
- `web-review` - Agente de revisión de código

### Skills
- `typescript-expert` - Tipos y configuración de TypeScript
- `express-expert` - Middleware y routing de Express.js
- `expo-expert` - SDK de Expo y React Native
- `supabase-expert` - PostgreSQL, RLS, Auth, Edge Functions
- `nextjs-expert` - App Router y Pages Router de Next.js
- `nestjs-expert` - Arquitectura y patrones de Nest.js
- `web-design-guidelines` - Revisión de UI/UX

### Reglas
- `AGENTS.md` - Reglas globales de desarrollo

## Servidores MCP

Servidores MCP remotos configurados:
- **context7** - Documentación y ejemplos de código
- **gh_grep** - Búsqueda de código en GitHub

Uso: Agrega `usa context7` o `usa la herramienta gh_grep` en los prompts.

## Uso de Skills

Invoca con `/skill <nombre>`:
- `/skill typescript-expert`
- `/skill express-expert`
- `/skill expo-expert`
- `/skill supabase-expert`
- `/skill nextjs-expert`
- `/skill nestjs-expert`
- `/skill web-design-guidelines`

## Uso de Agentes

Invoca con `/agent <nombre>`:
- `/agent mobile-dev`
- `/agent web-review`
