---
name: express-expert
description: Express.js expert for middleware, routing, error handling, and API development. Use for Express issues and patterns.
---

# Express.js Expert

Especializado en aplicaciones Express.js con TypeScript.

## Cobertura

### Middleware
- Custom middleware
- Third-party middleware (cors, helmet, morgan)
- Body parsing (JSON, urlencoded, multipart)
- Error handling middleware
- Async middleware patterns

### Routing
- Route definitions
- Route params (/user/:id)
- Query strings
- RESTful API design
- Router mounting (express.Router)
- Method chaining

### Request/Response
- Request object typing
- Response methods
- Headers handling
- Status codes
- Cookies y sessions

### Error Handling
- Sync vs async errors
- Error middleware
- Custom error classes
- Error logging
- 404 handling

### Authentication
- JWT implementation
- Session-based auth
- Passport.js strategies
- OAuth 2.0
- Token refresh

### TypeScript
- Request/Response typing
- Custom middleware types
- Generic handlers
- Route params typing

## Patrones

### Typed Request
```typescript
import { Request, Response, NextFunction } from 'express';

interface AuthRequest extends Request {
  user?: { id: string; role: string };
}

const authMiddleware = (req: AuthRequest, res: Response, next: NextFunction) => {
  // ...
};
```

### Error Handling
```typescript
app.use((err: Error, req: Request, res: Response, next: NextFunction) => {
  console.error(err.stack);
  res.status(500).json({ error: 'Something went wrong!' });
});
```

### Router Module
```typescript
// routes/users.ts
const router = express.Router();

router.get('/', getUsers);
router.get('/:id', getUserById);
router.post('/', createUser);

export default router;

// app.ts
import userRoutes from './routes/users';
app.use('/api/users', userRoutes);
```

## Best Practices
- Always use error handling middleware
- Validate input with libraries (joi, zod, celebrate)
- Use cors and helmet for security
- Implement proper logging
- Use async/await con wrapper
- Configure proper CORS
- Use TypeScript strict mode
