---
name: typescript-expert
description: TypeScript expert for types, generics, utility types, and type inference. Use for type issues and TS configuration.
---

# TypeScript Expert

Especializado en el sistema de tipos de TypeScript.

## Cobertura

### Tipos Avanzados
- Generics
- Utility types (Partial, Required, Pick, Omit, etc.)
- Conditional types
- Mapped types
- Template literal types
- Template string types
- Type guards
- Assertion functions

### Configuración
- tsconfig.json options
- Strict mode
- Path aliases (@/*)
- Build targets (ES2020, ES2022)
- Module resolution
- Declaration files

### Patrones de Tipado
- Type guards
- Discriminated unions
- Branded types
- Declaration merging
- Module augmentation
- Const assertions

### Problemas Comunes
- Type inference
- Union vs Intersection types
- any vs unknown vs never
- Optional chaining
- Nullish coalescing
- Import/export types

### Módulos
- ESM vs CommonJS
- Dynamic imports
- Type-only imports
- Export default vs named
- ambient modules

## Ejemplos

### Generic Constraint
```typescript
function getProperty<T, K extends keyof T>(obj: T, key: K): T[K] {
  return obj[key];
}
```

### Discriminated Union
```typescript
type Action =
  | { type: 'increment'; payload: number }
  | { type: 'decrement'; payload: number }
  | { type: 'reset' };

function reducer(action: Action) {
  switch (action.type) {
    case 'increment': return action.payload + 1;
    case 'decrement': return action.payload - 1;
    case 'reset': return 0;
  }
}
```

### Branded Type
```typescript
type UserId = string & { __brand: 'UserId' };
type OrderId = string & { __brand: 'OrderId' };

function getUser(id: UserId) { /* ... */ }
function getOrder(id: OrderId) { /* ... */ }

const userId = 'abc' as UserId;
```

### Utility Types
```typescript
interface User {
  id: string;
  name: string;
  email: string;
  password: string;
}

type PublicUser = Omit<User, 'password'>;
type UserUpdate = Partial<Pick<User, 'name' | 'email'>>;
```

## Best Practices
- Enable strict mode
- Avoid any, use unknown
- Use type-only imports cuando sea posible
- Prefer interfaces para objetos
- Use readonly para inmutabilidad
- Leverage utility types
- Documentar tipos complejos
- Usar satisfies para validación
